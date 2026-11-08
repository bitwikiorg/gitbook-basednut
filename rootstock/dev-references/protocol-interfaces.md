# Protocol Interfaces

Protocol interfaces are the formal boundaries between ROOTSTOCK components. They define **who may call what shape of function**, which data crosses the boundary, and which responsibilities remain on each side.

The inherited Balancer v3 interface families provide the current technical model. Exact ROOTSTOCK interface artifacts should be generated from the build that produced the deployed bytecode.

***

### Interface families

| Family                      | Primary responsibility                                        | Typical caller                        |
| --------------------------- | ------------------------------------------------------------- | ------------------------------------- |
| Vault                       | accounting, settlement, swaps, liquidity, pool state, queries | Routers / infrastructure              |
| Vault Admin                 | pausing, fee/config administration, recovery, buffer controls | authorized accounts/contracts         |
| Pool                        | invariant and swap/liquidity math                             | Vault                                 |
| Router                      | public workflows and query equivalents                        | users / apps / solvers                |
| Hook                        | lifecycle callbacks and dynamic fees                          | Vault                                 |
| Factory                     | instance creation and version provenance                      | deployers / builders                  |
| Protocol Fee Controller     | protocol + creator fee accounting and collection              | Vault / authorized fee administration |
| Authorizer / authentication | permission checks and role administration                     | protocol contracts / administrators   |
| Token / rate                | RPT ERC-20 behavior, rate providers, ERC-4626 assets          | Vault / apps                          |
| Contract Registry           | typed discovery, aliases, active/deprecated state             | apps / Routers / governance tooling   |

***

### Caller direction

{% code expandable="true" %}
```mermaid
%%{init: {"theme":"base","themeVariables":{
  "primaryColor":"#E7E0C3",
  "primaryTextColor":"#243018",
  "primaryBorderColor":"#6F7B48",
  "lineColor":"#7A6847",
  "secondaryColor":"#DCE8CB",
  "tertiaryColor":"#F3EBD8",
  "fontFamily":"Inter, ui-sans-serif, system-ui, sans-serif"
}}}%%
flowchart LR
    A["Application"] --> RI["Router interface"]
    RI --> VI["Vault interface"]
    VI --> PI["Pool interface"]
    VI -. configured callback .-> HI["Hook interface"]
    FI["Factory interface"] --> VI
    VI <--> FC["Fee-controller interface"]
    X["Indexer"] --> EV["Events + read interfaces"]

    classDef user fill:#F5F0E3,stroke:#8B7754,stroke-width:2px,color:#2E281D;
    classDef execution fill:#D5E3BE,stroke:#536B3F,stroke-width:3px,color:#1D2816;
    classDef market fill:#E8D9B9,stroke:#7A5C34,stroke-width:2px,color:#2C2116;
    classDef extension fill:#E3E8D5,stroke:#75845A,stroke-width:2px,color:#25301E;

    class A,X user;
    class RI,VI,EV execution;
    class PI,FI market;
    class HI,FC extension;
```
{% endcode %}

Applications should normally integrate through a Router rather than internal math interfaces. The Router gives the application a stable workflow boundary while the Vault and Pool retain their lower-level responsibilities.

***

### The Vault interface is composed

The inherited v3 Vault surface is not one small interface. It is composed from execution, extension/read, admin, event, and error surfaces.

A useful mental split is:

{% tabs %}
{% tab title="Execution" %}
Unlocking, settlement, swaps, liquidity operations, token movement, and buffer wrap/unwrap primitives.
{% endtab %}

{% tab title="Read / extension" %}
Pool registration/state, balances, rates, configuration, RPT accounting, fee reads, recovery reads, quote machinery, and authorization discovery.
{% endtab %}

{% tab title="Admin" %}
Pause state, fee/config setters, recovery controls, query controls, buffer administration, and authorizer replacement.
{% endtab %}
{% endtabs %}

See Vault API for the callable groups.

***

### Shared data types

Several types are part of the inherited cross-contract language. Important examples include:

| Type                  | Meaning                                                                       |
| --------------------- | ----------------------------------------------------------------------------- |
| `SwapKind`            | `EXACT_IN` or `EXACT_OUT`                                                     |
| `AddLiquidityKind`    | proportional, unbalanced, single-token exact-out, donation, custom            |
| `RemoveLiquidityKind` | proportional, single-token exact-in/out, custom                               |
| `TokenConfig`         | token, token type, rate provider, yield-fee flag                              |
| `PoolConfig`          | liquidity management, fee percentages, pause/registration/init/recovery state |
| `PoolRoleAccounts`    | pause manager, swap-fee manager, pool creator                                 |
| `HookFlags`           | callback capabilities a Hook requests                                         |
| `HooksConfig`         | enabled callback flags plus Hook contract address                             |
| `PoolSwapParams`      | normalized swap inputs passed to pool/hook logic                              |

Exact struct members and ordering are ABI facts. Use the generated interface/ABI for the deployment version you target.

***

### Interface compatibility is not economic compatibility

Two contracts can satisfy the same Solidity interface and still behave differently economically.

A custom Pool may implement the expected Vault callback while using a different invariant. A Hook can alter dynamic fees or adjusted amounts without changing the Pool ABI. Interface compatibility therefore answers **can these contracts communicate?** It does not answer **do these markets behave the same?**

Integrators that accept arbitrary Pools or Hooks need capability and trust checks in addition to ABI compatibility.

***

### Version binding

For every exact interface used by an integration, record:

* interface source path and commit/build identifier;
* compiler/build provenance where available;
* deployed chain and contract address;
* corresponding ABI artifact;
* version metadata exposed by the contract/factory, when available;
* whether the surface is intended for external callers or internal composition.

See ABIs, Deployments, and Repositories.
