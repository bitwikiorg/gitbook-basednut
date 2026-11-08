# Query & Simulate

## Query & Simulate

A **query** simulates a ROOTSTOCK operation against current protocol state and returns its expected economic result without committing the transaction.

Applications use queries to answer questions such as:

* How many tokens would this swap return?
* How much input would an exact-out swap require?
* How much RPT would this liquidity addition mint?
* What assets would this RPT removal return?
* What would this complete multihop route produce?

A query is a **pricing and transaction-construction tool**.

It is not a reservation and it does not guarantee that the same result will still be available when the transaction executes.

***

### Query the operation you will execute

The safest rule is:

> **Query the same economic operation, with the same relevant inputs, that you intend to execute.**

| Intended execution     | Corresponding query               |
| ---------------------- | --------------------------------- |
| Exact-in swap          | Exact-in swap query               |
| Exact-out swap         | Exact-out swap query              |
| Proportional add       | Proportional-add query            |
| Unbalanced add         | Unbalanced-add query              |
| Single-token add       | Same single-token-add query       |
| Proportional remove    | Proportional-remove query         |
| Single-token remove    | Same single-token-remove query    |
| Multihop / batch route | Same complete path                |
| Custom operation       | Corresponding pool-specific query |

Do not quote a simplified path and then execute a materially different one.

***

### The query must preserve relevant context

Matching only the operation name is not always enough.

Where relevant, the query should preserve:

* Root Pool;
* token addresses;
* token ordering;
* Exact In or Exact Out;
* liquidity-operation kind;
* exact amount being fixed;
* route and intermediate assets;
* `sender`;
* `userData`;
* wrapper or buffer choices;
* custom-pool parameters.

This matters because Hooks or custom logic can depend on the apparent sender or supplied data.

```
execution intent
+ pool / route
+ amounts
+ sender
+ userData
+ operation kind
        ↓
      query
        ↓
 expected calculated side
```

{% hint style="warning" %}
**Same destination is not necessarily the same operation.**

Two paths that both produce USDC → WETH can have different pools, fees, Hooks, rates, wrapper conversions, and resulting amounts.
{% endhint %}

***

### Typical integration workflow

```
construct intent
      ↓
query matching Router surface
      ↓
receive expected result
      ↓
apply execution policy
      ↓
minimum output / maximum input
      ↓
construct final transaction
      ↓
simulate final transaction where useful
      ↓
send
      ↓
verify execution
```

There are two distinct simulation layers in this workflow:

1. **protocol query** — calculates the economic result;
2. **transaction simulation** — tests the constructed transaction more broadly.

They answer different questions.

***

### Router query

A Router query asks:

> **What would this ROOTSTOCK operation calculate against this state?**

Examples include queries for:

* single-pool swaps;
* batch or multihop swaps;
* proportional liquidity;
* unbalanced liquidity;
* single-token liquidity;
* recovery removal;
* supported buffer operations;
* supported composite operations.

Use the public Router query corresponding to the execution Router whenever possible.

The exact function names and return values belong in Router APIs.

***

### Queries are offchain

In the inherited v3 architecture, Router query functions are intended to run in a **static offchain context**, normally through an RPC call such as `eth_call`.

They are not ordinary state-changing contract operations.

```
application
    ↓
RPC / eth_call
    ↓
Router query
    ↓
Vault query context
    ↓
Pool + Hook logic
    ↓
result returned
```

No execution transaction is submitted and no final protocol state is persisted.

{% hint style="warning" %}
**Do not build an onchain contract that queries the current result and then blindly uses that result as its own execution limit.**

The surrounding state and transaction ordering can be manipulated. An onchain integration should receive or derive an independently meaningful limit appropriate to its trust model.
{% endhint %}

***

### Queries do not require execution authorization

A query does not transfer the user's input assets or burn their RPT.

Under the inherited v3 Router model, ordinary queries therefore do not require:

* ERC-20 approval;
* Permit2 authorization;
* RPT allowance;
* permit signatures;
* actual token transfer.

This allows an application to estimate an operation **before** the user has prepared execution authorization.

Authorization belongs to the eventual state-changing transaction.

***

### Query state is not reserved

Suppose a query produces:

```
100 USDC
    ↓
query
    ↓
0.040 WETH
```

That means:

> Against the state observed by the query, this operation calculates approximately 0.040 WETH.

It does **not** mean ROOTSTOCK has reserved that result.

Before execution, any relevant state can change.

Examples include:

* pool balances;
* another swap;
* another liquidity operation;
* static swap-fee configuration;
* dynamic fee output;
* Hook state;
* token rates;
* buffer state;
* pool pause state;
* Recovery Mode state;
* block timestamp;
* other external state read by configured logic.

The transaction must therefore protect itself independently of the quote.

***

### Record the state behind important quotes

For production routing and debugging, it is useful to preserve the context in which a quote was obtained.

Depending on the application, that can include:

* chain;
* block number or block tag;
* timestamp;
* Router;
* Root Pools;
* route;
* input parameters;
* output result;
* sender used for the query;
* relevant `userData`.

This gives the quote provenance.

```
quote
├── operation
├── route
├── parameters
├── state reference
└── result
```

Quote age is useful operational information, but age alone does not determine whether a quote is still valid.

A one-second-old quote can be stale after a large intervening transaction.

A much older quote may remain close to executable if relevant state has not moved.

***

### From quote to execution limit

The query estimates the **calculated side**.

The application then turns that estimate into an enforceable boundary.

#### Exact In

Suppose:

```
exact input  = 100 units
quoted output = 100 units
```

With a policy allowing a `0.5%` adverse move:

```
minimum output
= quoted output × (1 - tolerance)

= 100 × 0.995
= 99.5
```

After conversion to the token's integer units and the application's chosen rounding policy, that minimum becomes part of the execution transaction.

#### Exact Out

Suppose:

```
exact output = 100 units
quoted input = 50 units
```

A corresponding maximum-input policy might be:

```
maximum input
= quoted input × (1 + tolerance)
```

The direction reverses because the calculated side is now the amount being spent.

{% hint style="info" %}
**Quote → expectation**

**Limit → acceptance boundary**

A quote helps construct the limit. The limit protects execution.
{% endhint %}

See Price Impact & Slippage.

***

### Protocol rounding still applies

Application slippage tolerance is not the same thing as protocol rounding.

They are separate layers.

```
pool / Vault math
    ↓
protocol rounding rules
    ↓
quoted result
    ↓
application tolerance
    ↓
execution limit
```

The inherited v3 accounting system applies its own fixed-point and pool-favoring rounding rules during calculations.

The application then applies its separate execution policy to the resulting quote.

Do not attempt to replace protocol rounding with application-side decimal arithmetic.

See Rounding & Invariant Approximation.

***

### Router query vs transaction simulation

These two checks overlap, but they are not equivalent.

#### Router query

Primarily answers:

> **What amount would the economic operation calculate?**

Useful for:

* expected swap output;
* expected swap input;
* expected RPT result;
* expected removal amounts;
* route comparison;
* limit construction.

#### Final transaction simulation

Primarily answers:

> **Would this constructed transaction execute successfully against the simulated state?**

Depending on the simulation method and node/provider, it can help expose problems such as:

* insufficient balance;
* missing approval;
* incorrect authorization;
* incorrect sender assumptions;
* expired deadline;
* failed execution limits;
* Hook reverts;
* permission failures;
* wrong calldata;
* wrong ETH `value`;
* incompatible token behavior;
* another contract-level revert.

```
Router query
    ↓
economic result

final calldata
    ↓
transaction simulation
    ↓
execution viability
```

{% hint style="success" %}
For important production transactions, use the economic query to build the operation and a final transaction simulation when practical to validate the assembled call.
{% endhint %}

Gas estimation is a separate check and should use the appropriate RPC or simulation facility rather than treating the economic Router query as a gas estimate.

***

### Query does not prove execution success

A successful economic query does not necessarily mean the final transaction will succeed.

For example:

```
query succeeds
      ↓
expected output known
```

but execution can still fail because:

```
approval missing
deadline expired
balance insufficient
limit too strict
wrong msg.value
pool state changed
authorization changed
```

This is another reason not to collapse querying and transaction simulation into one concept.

***

### Low-level quote machinery

Applications normally should use the public Router query interfaces.

The inherited v3 Vault also exposes lower-level mechanisms that Router implementations can use for more complex simulations.

#### `quote`

The Router can enter a Vault **quote context** and execute query logic through the same transient-accounting machinery used by protocol operations.

This makes it possible to simulate composed operations.

Within that simulated context, earlier simulated operations can affect later operations in the same composition.

That behavior is useful when the intent is to model a sequence.

#### `quoteAndRevert`

Sometimes the goal is different:

> Compare multiple scenarios against the **same initial state**.

The inherited v3 architecture provides `quoteAndRevert` for this class of problem.

Conceptually:

```
initial state
     ↓
simulate scenario
     ↓
produce result
     ↓
revert simulation
     ↓
initial state preserved
```

The result is encoded through the revert path and decoded by the calling infrastructure.

`quoteAndRevert` is explicitly an offchain mechanism.

{% hint style="info" %}
`quote` and `quoteAndRevert` are **advanced Router / Vault machinery**.

They should not replace the normal public Router query interface in ordinary application integrations.
{% endhint %}

Exact callback interfaces and revert decoding belong in Vault API and Build a Custom Router.

***

### Querying composed routes

A multihop or multiple-path transaction should be queried as the composed route that will actually execute.

For example:

```
A → Pool 1 → B → Pool 2 → C
```

should be queried as that path rather than as:

```
A → C
```

using an unrelated simplified estimate.

Likewise, if execution includes a supported wrapper or buffer step:

```
A → Pool → wrapped asset → buffer → underlying
```

the query should model that path where the deployed Router provides the corresponding query surface.

Each additional execution layer can affect the final result.

***

### Sender and `userData` can matter

Queries are not always purely a function of:

```
pool + token + amount
```

The inherited Router interfaces can explicitly accept a `sender` and `userData`.

That allows the simulated operation to preserve context that may influence:

* Hooks;
* custom pool behavior;
* pool-specific parameters;
* caller-dependent logic.

Therefore:

```
query(sender = Alice)
```

should not automatically be assumed equivalent to:

```
execute(sender = Bob)
```

when attached logic can distinguish them.

***

### Query failures are useful information

A query can fail before any transaction is sent.

Possible causes include:

* invalid Root Pool;
* unsupported operation;
* invalid token;
* incorrect token ordering;
* invalid route;
* incompatible `userData`;
* Hook revert;
* pool state restrictions;
* buffer or wrapper failure;
* malformed parameters;
* unavailable query functionality on the deployed protocol version.

Do not silently convert a failed query into a zero quote.

A query failure should be treated as a distinct integration result and surfaced or handled explicitly.

***

### Freshness policy

Applications should choose quote-refresh behavior based on how quickly the relevant state can change.

High-activity markets may justify frequent refreshes.

Low-activity markets may not.

The relevant question is not simply:

> How old is the quote?

It is:

> How much relevant state could have changed since the quote?

Regardless of refresh policy, the transaction's encoded minimum or maximum remains the final execution boundary.

***

### Verification after execution

A query describes expected execution.

The receipt describes what actually happened.

Production systems should preserve both when useful:

```
quote
    ↓
transaction limits
    ↓
execution
    ↓
receipt
```

Comparing them can help identify:

* normal state movement;
* routing drift;
* stale quoting;
* changing rates;
* dynamic fee changes;
* Hook effects;
* incorrect assumptions;
* integration bugs.

The quote should never overwrite the executed result in accounting or analytics.

***

### Integration invariant

The complete model is:

```
intent
   ↓
query same operation
   ↓
expected calculated side
   ↓
apply application policy
   ↓
encode min / max limit
   ↓
construct transaction
   ↓
simulate full transaction where useful
   ↓
execute
   ↓
verify actual result
```

\*\*Query predicts.\*\*

**Limit protects.**

\*\*Transaction simulation tests the assembled
