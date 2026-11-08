# 09 - Price Impact and Slippage

A quoted price is not the same as an executable outcome.

This distinction becomes important the moment your trade is large relative to available liquidity or market conditions move between quote and settlement.

{% hint style="warning" %}
**Do not solve bad execution by making your protections weaker.**
{% endhint %}



***

## ⚖️ Two different problems

{% tabs %}
{% tab title="Price impact" %}
The effect **your trade itself** has on the available liquidity and resulting execution price.
{% endtab %}

{% tab title="Slippage" %}
The difference between expected execution and the final execution caused by market movement or changing state between quote and settlement.
{% endtab %}
{% endtabs %}

Uniswap's documentation explicitly distinguishes these concepts.

They are related but not interchangeable.



***

## 🧪 Trade-size experiment

Open a NUT-related route on Uniswap, Balancer, or Aerodrome.

Do not submit anything.

Compare several sizes:

```
very small
small
medium
large relative to pool
```

Record:

* quoted output;
* price impact;
* route;
* fee information;
* minimum received or equivalent protection.

As size grows, you may see execution deteriorate.

That is liquidity becoming visible.



***

## 🛡️ Slippage tolerance

A slippage setting allows the transaction to tolerate some movement.

Too tight:

```
market moves slightly
      ↓
transaction reverts
      ↓
gas may still be spent
```

Too loose:

```
transaction can accept much worse execution
```

The correct tolerance depends on asset volatility, liquidity, route, transaction design, and market conditions.

There is no universal “safe slippage percentage.”



***

## 🚨 The dangerous beginner move

A transaction refuses to execute.

The interface says slippage is too low.

The user raises it repeatedly until the trade goes through.

That can be equivalent to saying:

> “I do not understand why the market is refusing this price, so I will authorize a worse one.”

Stop and diagnose first.

Possible causes include:

* volatile price;
* thin liquidity;
* unusual token mechanics;
* route instability;
* stale quote;
* transaction taxes/fees;
* incorrect asset;
* malicious or broken interface.

***

## 🧭 Compare venues by executable output

Suppose the same trade is available through:

* Uniswap;
* Balancer;
* Aerodrome.

Compare:

```
net token output
route
price impact
DEX/pool fees
network cost
execution protection
```

Do not compare screenshots of spot prices.

A venue with a superficially better spot price can produce worse execution for your size.



***

## 🕳️ MEV and ordering

Public blockchain transactions exist in an environment where ordering can matter.

Other actors may observe or react to pending transactions depending on the transaction path and infrastructure.

You do not need to master MEV to understand the safety lesson:

> A transaction can face execution conditions that differ from the moment you clicked Review.

Slippage protections and minimum-out constraints are part of controlling that uncertainty.



***

## ⚠️ Thin liquidity changes everything

If a token has shallow liquidity:

* small trades can move price substantially;
* quoted market capitalization may be misleading as an exit metric;
* entering may be easier than exiting at the same apparent price;
* arbitrage can be limited by costs and available venues.

Liquidity is not the same as token supply or market capitalization.



***

## 🌰 BASED NUT practice

Before any meaningful NUT swap:

{% stepper %}
{% step %}
## Inspect pool depth or route

Understand roughly where execution comes from.
{% endstep %}

{% step %}
## Compare trade sizes

Find where price impact begins changing materially.
{% endstep %}

{% step %}
## Check protections

Know the minimum outcome you are authorizing.
{% endstep %}

{% step %}
## Reject unexplained deterioration

If the quote becomes materially worse, diagnose rather than forcing it through.
{% endstep %}
{% endstepper %}



***

## 🧪 Operational lab: measure execution rather than reading a single quote

Use **Uniswap/Aerodrome/Balancer + Dune + BaseScan**. No funds need to move until the final optional step.

{% stepper %}
{% step %}
## Build a quote ladder

For the same token pair, request several input sizes—for example 1×, 5×, 10×, and 25× a small base amount. Record quoted output, price impact, and minimum output.
{% endstep %}

{% step %}
## Compare venues

Check at least two canonical DEX routes if the market exists on both. Compare **net executable output**, not merely displayed spot price.
{% endstep %}

{% step %}
## Inspect historical execution

In Dune, query Base `dex.trades` for the pair/protocol and inspect multi-hop execution legs. Use timestamps and transaction hashes to open representative trades on BaseScan.
{% endstep %}

{% step %}
## Learn the ordering problem

Read CoW Protocol’s security/MEV educational material to understand why public transaction ordering can affect execution. Then distinguish MEV exposure from ordinary AMM price impact and user-configured slippage tolerance.
{% endstep %}

{% step %}
## Optional: execute only the smallest rung

If you perform the test, execute the smallest trade and calculate realized execution from final token deltas. Do not call the realized price the pre-trade quote.
{% endstep %}
{% endstepper %}

***

## 🔗 Learn more

* [Uniswap — Price Impact vs Price Slippage](https://support.uniswap.org/hc/en-us/articles/8643794102669-Price-Impact-vs-Price-Slippage)
* [CoW — DeFi Security Explained](https://cow.fi/learn/de-fi-security-explained-from-transactional-threats-to-protocol-vulnerabilities-and-beyond)
* [Dune Docs](https://docs.dune.com/)
* [DeFiLlama — DEX analytics](https://defillama.com/dexs)



***

## 📐 Final model

```
spot price
   ≠
quoted price
   ≠
executed price

execution quality
   =
liquidity
+ trade size
+ route
+ fees
+ market movement
+ transaction conditions
```

Price is a number.

Execution is a process.
