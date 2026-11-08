# Exact In & Exact Out

Every swap has two sides:

```
Token A in → Token B out
```

The swap mode determines **which amount is fixed before execution and which amount the pool must calculate**.

* **Exact In:** fix what you spend; calculate what you receive.
* **Exact Out:** fix what you receive; calculate what you must spend.

{% hint style="success" %}
**The pool and invariant do not change between the two modes. Only the known side of the trade changes.**
{% endhint %}

***

### Two ways to express the same trade

{% tabs %}
{% tab title="Exact In" %}
With **Exact In**, the input amount is fixed.

```
I will spend exactly 100 Token A.
How much Token B will I receive?
```

The pool calculates the output amount.

The transaction also defines a **minimum amount out**. If execution would return less than that minimum, the swap reverts.

Exact In is useful when the amount you are willing to spend is already known.
{% endtab %}

{% tab title="Exact Out" %}
With **Exact Out**, the output amount is fixed.

```
I want exactly 100 Token B.
How much Token A must I spend?
```

The pool calculates the required input amount.

The transaction also defines a **maximum amount in**. If execution would require more than that maximum, the swap reverts.

Exact Out is useful when the amount you need to receive is already known.
{% endtab %}
{% endtabs %}

***

### Comparison

| Property                  | Exact In              | Exact Out              |
| ------------------------- | --------------------- | ---------------------- |
| **Fixed amount**          | Input                 | Output                 |
| **Calculated amount**     | Output                | Input                  |
| **Execution protection**  | Minimum output        | Maximum input          |
| **Conservative rounding** | Output rounds down    | Input rounds up        |
| **Typical intent**        | Fixed spending amount | Fixed receiving amount |

The distinction is therefore not about two different markets. It is two ways of asking the same market for a trade.

***

### Limits define acceptable execution

The fixed amount tells the protocol **what must remain exact**.

The limit tells the protocol **how much variation is acceptable on the calculated side**.

{% tabs %}
{% tab title="Exact In" %}
```
exact input:   100 A
minimum out:    95 B
```

The transaction may execute if the calculated output is at least `95 B`.

```
97 B → allowed
95 B → allowed
94 B → revert
```
{% endtab %}

{% tab title="Exact Out" %}
```
exact output:  100 B
maximum in:    110 A
```

The transaction may execute if the calculated input is no more than `110 A`.

```
105 A → allowed
110 A → allowed
111 A → revert
```
{% endtab %}
{% endtabs %}

The limit protects the side of the trade that is **not fixed**.

See Price Impact & Slippage.

***

### Fees are always input-side

Both modes pay the configured swap fee, but the calculation reaches that fee from opposite directions.

#### Exact In

The caller already knows the total input.

The swap fee is calculated from that amount and removed before the remaining input reaches the pool's pricing calculation.

```
exact input
    ↓
swap fee removed
    ↓
net input priced by pool
    ↓
output calculated
```

#### Exact Out

The caller already knows the desired output.

The pool first determines how much input is required for that output. The swap fee is then incorporated into the final amount the caller must provide.

```
exact output
    ↓
pool calculates required input
    ↓
swap fee added
    ↓
final input required
```

{% hint style="info" %}
**Exact In and Exact Out change the direction of the calculation, not the obligation to pay the configured swap fee.**
{% endhint %}

Detailed fee configuration belongs in Fees & LP Returns and Dynamic Fees.

***

### Rounding follows the same principle

Onchain pool mathematics uses fixed-point arithmetic, so some calculated values cannot be represented perfectly.

ROOTSTOCK follows the inherited conservative rule:

> **Amounts the caller receives round down. Amounts the caller pays round up.**

That produces opposite visible rounding behavior for the two swap modes.

{% tabs %}
{% tab title="Exact In" %}
The input is already fixed.

The calculated **output rounds down**.

```
mathematical result: 98.123456... B
onchain result:       ≤ that amount
```

The caller never receives more because of rounding.
{% endtab %}

{% tab title="Exact Out" %}
The output is already fixed.

The calculated **input rounds up**.

```
mathematical requirement: 103.456789... A
onchain requirement:       ≥ that amount
```

The caller never pays less because of rounding.
{% endtab %}
{% endtabs %}

This protects the pool from value being extracted through accumulated rounding errors.

***

### How routed trades propagate amounts

The distinction becomes especially useful when a route contains several swaps.

#### Exact In moves forward

Start with the known input and calculate each successive output.

```
100 A fixed
   ↓
Pool 1
   ↓
B calculated
   ↓
Pool 2
   ↓
C calculated
   ↓
final output
```

The output of one step can become the input of the next.

The final constraint is the route's **minimum acceptable output**.

#### Exact Out solves backward

Start with the desired final output and determine what the preceding step must provide.

```
100 C required
   ↑
Pool 2
   ↑
required B
   ↑
Pool 1
   ↑
required A
```

Conceptually, the required amounts propagate backward through the route until the initial input requirement is known.

The final constraint is the route's **maximum acceptable input**.

{% hint style="info" %}
The Exact Out diagram describes the **calculation dependency**, not the physical direction of token movement. Tokens still move from the input asset toward the output asset during execution.
{% endhint %}

See Batch & Multihop Swaps.

***

### A quote is not an execution guarantee

Before submitting a trade, an application can query the protocol to estimate the calculated side of the swap.

For example:

```
Exact In query
100 A → estimated 98 B
```

or:

```
Exact Out query
100 B ← estimated 103 A required
```

A query reflects the state used for that simulation. Pool balances, rates, fees, or other relevant state can change before the transaction executes.

The **quote** answers:

> What would this swap return against the observed state?

The **limit** answers:

> What is the worst execution I am willing to accept?

Those are different jobs.

{% hint style="warning" %}
Do not treat a query result as the transaction's protection. Execution limits must independently bound the acceptable result.
{% endhint %}

See Queries & Simulation.

***

### Continue

<table data-full-width="true"><thead><tr><th width="227.5">Page</th><th>What it explains</th></tr></thead><tbody><tr><td><strong>Swap Lifecycle</strong></td><td>Where swap mode, fees, pool math, accounting, Hooks, and settlement enter the transaction.</td></tr><tr><td><strong>Price Impact &#x26; Slippage</strong></td><td>Why execution can differ from an initial quote and how limits protect the trade.</td></tr><tr><td><strong>Batch &#x26; Multihop Swaps</strong></td><td>How Exact In and Exact Out propagate through routes containing several steps.</td></tr><tr><td><strong>Queries &#x26; Simulation</strong></td><td>How applications estimate swap outcomes without executing the trade.</td></tr><tr><td><strong>Swap Guide</strong></td><td>How to construct and execute swaps from an integration.</td></tr></tbody></table>
