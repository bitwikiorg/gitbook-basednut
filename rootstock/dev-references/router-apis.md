# Router APIs

Routers are ROOTSTOCK's normal public execution layer. They turn user intent into Vault operations while handling the workflow details that applications should not repeatedly reimplement.

Different Router contracts specialize in different workflows, but they can all operate against the same Vault and Pool system.

***

### Basic Router

The inherited Basic Router groups the common single-pool workflows.

#### Initialize

* `initialize`

#### Add liquidity

* `addLiquidityProportional`
* `addLiquidityUnbalanced`
* `addLiquiditySingleTokenExactOut`
* `donate`
* `addLiquidityCustom`

#### Remove liquidity

* `removeLiquidityProportional`
* `removeLiquiditySingleTokenExactIn`
* `removeLiquiditySingleTokenExactOut`
* `removeLiquidityCustom`
* `removeLiquidityRecovery`

#### Swap

* `swapSingleTokenExactIn`
* `swapSingleTokenExactOut`

The Basic Router exposes query counterparts for its add/remove/swap workflows:

| Execution                            | Query                                     |
| ------------------------------------ | ----------------------------------------- |
| `addLiquidityProportional`           | `queryAddLiquidityProportional`           |
| `addLiquidityUnbalanced`             | `queryAddLiquidityUnbalanced`             |
| `addLiquiditySingleTokenExactOut`    | `queryAddLiquiditySingleTokenExactOut`    |
| `addLiquidityCustom`                 | `queryAddLiquidityCustom`                 |
| `removeLiquidityProportional`        | `queryRemoveLiquidityProportional`        |
| `removeLiquiditySingleTokenExactIn`  | `queryRemoveLiquiditySingleTokenExactIn`  |
| `removeLiquiditySingleTokenExactOut` | `queryRemoveLiquiditySingleTokenExactOut` |
| `removeLiquidityCustom`              | `queryRemoveLiquidityCustom`              |
| `removeLiquidityRecovery`            | `queryRemoveLiquidityRecovery`            |
| `swapSingleTokenExactIn`             | `querySwapSingleTokenExactIn`             |
| `swapSingleTokenExactOut`            | `querySwapSingleTokenExactOut`            |

`initialize` and `donate` do not have matching query methods in the inherited `IRouter` interface.

{% hint style="success" %}
**Query the operation you intend to execute.** Do not quote a different liquidity kind or swap direction and assume the result is interchangeable.
{% endhint %}

***

### Router common surface

Inherited Router infrastructure also exposes shared helpers such as:

* `getVault`;
* `getWeth`;
* `getPermit2`;
* `permitBatchAndCall`;
* `multicall`.

Retail-facing Routers commonly use Permit2 and native-token helpers to reduce approval and wrapping boilerplate around the core Vault call.

***

### Batch Router

The Batch Router is the multihop/batched swap surface.

<table><thead><tr><th width="360">Execution</th><th>Query</th></tr></thead><tbody><tr><td><code>swapExactIn</code></td><td><code>querySwapExactIn</code></td></tr><tr><td><code>swapExactOut</code></td><td><code>querySwapExactOut</code></td></tr></tbody></table>

A path can traverse several steps/pools. The Router handles the composed execution while the Vault settles the resulting accounting atomically.

Query results can depend on sender context when Hooks inspect the sender, so use the same relevant caller assumptions for quote and execution.

***

### Buffer Router

The Buffer Router specializes in ERC-4626 buffer workflows. The inherited public interface includes:

* `initializeBuffer`;
* `addLiquidityToBuffer`;
* `queryInitializeBuffer`;
* `queryAddLiquidityToBuffer`;
* `queryRemoveLiquidityFromBuffer`.

A subtle but important boundary: the inherited `IBufferRouter` does **not** expose a state-changing `removeLiquidityFromBuffer` method. Buffer removal is implemented on the Vault Admin surface as an authenticated operation, with ownership and trusted-Router assumptions enforced around that path. Do not infer an execution method from the presence of the matching query method.

***

### Composite Liquidity Router

The Composite Liquidity Router combines wrapper and Pool operations so applications can work with ERC-4626-backed and nested liquidity without manually composing every wrap, unwrap, add, and remove step.

Its inherited interface exposes paired execution/query methods for two families:

| Family                       | Execution                                    | Query                                             |
| ---------------------------- | -------------------------------------------- | ------------------------------------------------- |
| ERC-4626 unbalanced add      | `addLiquidityUnbalancedToERC4626Pool`        | `queryAddLiquidityUnbalancedToERC4626Pool`        |
| ERC-4626 proportional add    | `addLiquidityProportionalToERC4626Pool`      | `queryAddLiquidityProportionalToERC4626Pool`      |
| ERC-4626 proportional remove | `removeLiquidityProportionalFromERC4626Pool` | `queryRemoveLiquidityProportionalFromERC4626Pool` |
| nested unbalanced add        | `addLiquidityUnbalancedNestedPool`           | `queryAddLiquidityUnbalancedNestedPool`           |
| nested proportional remove   | `removeLiquidityProportionalNestedPool`      | `queryRemoveLiquidityProportionalNestedPool`      |

Use this Router when the user's economic intent spans both a wrapper/nested layer and Pool liquidity.

***

### Unbalanced Add Via Swap Router

The inherited `IUnbalancedAddViaSwapRouter` composes a swap with a liquidity add so a two-token Pool can accept a contribution that begins off-ratio.

Its public workflow includes `addLiquidityUnbalanced` and `queryAddLiquidityUnbalanced`. The interface distinguishes the **exact** contribution from the **maximum adjustable** amount and rejects invalid combinations.

This Router is specialized behavior, not a replacement for the normal unbalanced-liquidity path on every Pool.

***

### Aggregator Routers

Upstream Balancer v3 also defines Router variants for aggregator/prepaid execution. Those surfaces assume a different settlement model: a smart-contract caller can pre-position tokens in the Vault instead of using the retail Permit2/native-token workflow.

{% hint style="warning" %}
An upstream Router family is not automatically a ROOTSTOCK deployment. Check Deployments before integrating a specialized Router.
{% endhint %}

***

### Current Base Sepolia Router set

The current ROOTSTOCK Base Sepolia application integration publishes addresses for these Router families:

* Basic Router;
* Batch Router;
* Buffer Router;
* Composite Liquidity Router;
* Unbalanced Add Via Swap Router.

See Deployments for addresses and provenance. Aggregator Routers are not included in the published Base Sepolia address map used by the current integration.

***

### Execution concerns

Every state-changing Router call should be evaluated for:

<table><thead><tr><th width="196">Concern</th><th>Why it matters</th></tr></thead><tbody><tr><td>sender</td><td>Hooks/permissions may depend on caller identity</td></tr><tr><td>recipient</td><td>output or RPT ownership may differ from sender</td></tr><tr><td>approvals / Permit2</td><td>determines which token movement is authorized</td></tr><tr><td>deadline</td><td>bounds stale execution where exposed</td></tr><tr><td>min output / max input</td><td>enforces user slippage limits</td></tr><tr><td>native token / WETH</td><td>changes calldata value and wrapping path</td></tr><tr><td>pool state</td><td>initialization, pause, recovery, token configuration</td></tr><tr><td>Hook behavior</td><td>can affect fees or adjusted amounts</td></tr><tr><td>query parity</td><td>quote and execution should represent the same workflow</td></tr></tbody></table>

***

### Capability-based integration

Do not bind application logic to one Router address forever.

A robust integration resolves:

```
chain
  → deployment version
    → available Router family
      → supported operation
        → matching ABI + query
```

That capability layer lets ROOTSTOCK add or replace specialized Routers without pretending that the underlying Vault or Pool interfaces changed.
