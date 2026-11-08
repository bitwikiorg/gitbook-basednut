# 🐞 NUT Structural Liquidity

{% hint style="danger" %}
### **WARNING: YOU ARE READING** HYPER ADVANCED NUT RESEARCH

We have exhausted the practical explanations and are now investigating what happens when very smart people are left alone with **1 NUT** for too long. The whitepaper needed more symbols. Advanced theory needed more equations. Apparently neither was enough. Welcome to the part where we give the NUT a research PhD program.
{% endhint %}

NUT has one invariant monetary quantity:

$$
S_{NUT}=1
$$

But that one NUT can occupy many different economic positions.



Some NUT may be:

* available in an AMM
* concentrated inside a narrow price range
* committed as collateral
* held inside an index
* sitting in wallets
* economically inaccessible

The amount of NUT has not changed.



Its **liquidity structure** has.

> **Structural liquidity is the economic configuration of where NUT is available, how deeply it can be traded, and through which markets it can move.**



### Supply Is Not Liquidity

These variables should not be confused.



NUT supply can remain unchanged:

$$
\Delta S_{NUT}=0
$$

while liquidity changes:

$$
\Delta L\neq0
$$

reserves change:

$$
\Delta R\neq0
$$

and routing changes:

$$
\Delta G\neq0
$$

Moving 0.01 NUT from a wallet into a pool does not create NUT.

But it can create:

* additional market depth
* a new executable route
* a different local price
* different arbitrage opportunities
* greater accessible float

NUT therefore has **monetary conservation with structural mobility**.



***

### Liquidity Depth

**Liquidity depth** describes how much trading can occur before execution price changes substantially.



A shallow NUT pool responds strongly to a trade.

A deep NUT pool responds less.



This means two pools containing NUT can have completely different economic importance even when both exist as valid markets.



Depth depends on the market design.

For concentrated liquidity it also depends on where LPs placed their liquidity.



### Active Liquidity

In concentrated-liquidity markets, deposited capital is not necessarily active at the current price.

Liquidity can exist outside the active range.



Therefore:

$$
\text{total deposited liquidity}
\neq
\text{current executable liquidity}
$$



For NUT, a useful structural analysis should distinguish:

* total liquidity
* active liquidity
* liquidity by price range
* depth at a particular trade size
* marginal price impact

This is more informative than TVL alone.



***

### Liquidity as Conductance

A useful analogy is **conductance**.

In physics and network theory, conductance describes how easily something can move through a system.



For NUT, we can use the idea to describe how easily economic quantity can move through a market without significantly moving price.



One possible local measure is:

$$
\kappa=
\left|
\frac{d\ln p}{dq}
\right|^{-1}
$$

where:

* $$p$$ is price
* $$q$$ is trade quantity
* $$\kappa$$ is local liquidity conductance

Large $$\kappa$$ means more NUT can move before price changes substantially.

Small $$\kappa$$ means the route has less executable depth.



This is an analytical measure, not a protocol invariant.

Different AMMs may require different implementations.



***

### The NUT Trunk and Branches

NUT liquidity can also be classified by economic role.



#### Core Liquidity

Some liquidity provides persistent:

* executable markets
* reference prices
* routing continuity
* depth

This can be thought of as the **trunk** of NUT liquidity.



#### Adaptive Liquidity

Other liquidity may move in response to:

* fees
* incentives
* volatility
* arbitrage
* new markets
* LP strategy

This behaves more like **branches**.

These categories describe economic function.

They do not require a particular owner or governance structure.



### Effective Float

NUT supply is always one.

But not every fraction of that NUT is equally accessible to the market.



Define each economic compartment as ii with NUT allocation:

$$
x_i
$$

and an accessibility coefficient:

$$
a_i\in[0,1]
$$

Then define effective float:

$$
F=
\sum_i a_i x_i
$$

with:

$$
0\leq F\leq1
$$



An accessibility coefficient expresses how economically available that NUT is.

For example:

* readily tradable NUT may have high accessibility
* deeply locked collateral may have lower accessibility
* irrecoverable NUT may approach zero

The exact coefficients must be defined empirically.

They should not be chosen merely to produce a desired result.



***

### Where Price Discovery Happens

A pool holding the most NUT does not automatically determine NUT's price.

**Price discovery** means the process through which trading produces the market's most economically influential price.



Price discovery depends on:

* active depth
* volume
* fees
* routing
* arbitrage speed
* trade size
* connectivity to external assets

The locus of NUT price discovery can therefore migrate between venues without any change in NUT supply.



***

### Reallocation Instead of Issuance

Many monetary systems can respond to changing demand partly through changing supply.

NUT cannot.

Its root quantity is fixed.



Pressure therefore resolves through variables such as:

* price
* allocation
* liquidity placement
* collateral commitment
* market depth
* routing

This makes the question:

> **Where is the NUT?**

economically important.



The quantity cannot adapt.

Its placement can.



***

### What We Can Measure

Structural NUT liquidity can be studied through:

* active liquidity by venue
* depth at standardized trade sizes
* price impact
* effective float
* NUT concentration by mechanism
* liquidity-range distribution
* liquidity migration
* routing capacity
* venue share of price discovery

The research question is:

> **How much of NUT's behavior comes from liquidity structure rather than monetary quantity?**

Because monetary quantity never changes, NUT provides an unusually constrained environment in which to investigate that distinction.

### Resources

* **Wikipedia — Market liquidity**
* **Wikipedia — Concentrated liquidity**
* **Wikipedia — Price discovery**
* **Wikipedia — Graph theory**
* **Wikipedia — Network theory**

These resources provide general terminology. NUT's structural-liquidity model is specific to the relationships surrounding NUT.
