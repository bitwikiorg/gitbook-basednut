# 💧 NUT Liquidity Machine

{% hint style="danger" %}
### **WARNING: YOU ARE READING** HYPER ADVANCED NUT RESEARCH

We have exhausted the practical explanations and are now investigating what happens when very smart people are left alone with **1 NUT** for too long. The whitepaper needed more symbols. Advanced theory needed more equations. Apparently neither was enough. Welcome to the part where we give the NUT a research PhD program.
{% endhint %}

NUT has a fixed supply of exactly one token.

$$
S_{NUT}=1
$$

That quantity does not change when NUT is traded, deposited into liquidity, committed as collateral, included in an index, or moved between wallets.

What changes is **where NUT is and what economic relationships surround it**.



This creates a useful way of understanding NUT:

> **NUT is conserved, but the market around NUT is continuously changing.**



***

### A Market Changes When NUT Moves Through It

Consider a NUT liquidity pool.

A swap does not simply transfer NUT through a passive pipe.

The trade also changes the pool.



Depending on the mechanism, a NUT transaction can change:

* reserves
* price
* active liquidity
* ticks
* pool balances
* subsequent price impact
* subsequent arbitrage opportunities

The market after the transaction is therefore different from the market before it.



This gives us the basic NUT liquidity cycle:

$$
\text{market state}
\rightarrow
\text{opportunity}
\rightarrow
\text{NUT transaction}
\rightarrow
\text{new market state}
$$



Repeated continuously:

$$
\text{state}
\rightarrow
\text{incentive}
\rightarrow
\text{transaction}
\rightarrow
\text{new state}
\rightarrow
\text{new incentive}
$$



We call this the **NUT Liquidity Machine**.

A **state** simply means the information required to describe the system at a particular moment: balances, reserves, liquidity, prices, parameters, and other economically relevant variables.



***

### Pools as State Transitions

A **state transition** is an operation that changes one valid state into another valid state.

Let the current NUT ecosystem state be:

$$
\Omega_t
$$

A market operation can be represented as:

$$
T(\Omega_t,q)
\rightarrow
(\Omega_{t+1},q')
$$

where:

* $$T$$ is the market operation
* $$q$$ is the input quantity
* $$q'$$ is the output quantity
* $$\Omega_t$$ is the state before execution
* $$\Omega_{t+1}$$ is the state afterward

For NUT, different mechanisms implement different transitions.



Examples include:

* swapping NUT/WETH on Uniswap V2
* swapping NUT/WETH through concentrated liquidity on Uniswap V3
* swapping NUT/AERO on Aerodrome
* swapping NUT/cbBTC
* locking NUT into a bonding curve
* releasing NUT from a bonding curve
* joining or exiting a structure containing NUT



These mechanisms do not merely quote NUT differently.

They transform different parts of NUT's economic state.



***

### Routes Are Composed Operations

NUT does not need to travel through only one market.

A trade can pass through several mechanisms.



For example:

```
NUT → AERO → WETH
```

or:

```
NUT → child token → external market → NUT
```



When one operation feeds another, the operations are **composed**.



**Function composition** means taking the output of one operation and using it as the input of the next.

For three transitions:

$$
T_1,\ T_2,\ T_3
$$

the complete route is:

$$
T_3\circ T_2\circ T_1
$$

The symbol $$\circ$$ means “apply one transformation after another.”

A NUT route is therefore more than a line connecting tokens.

It is an ordered sequence of state-changing operations

***

### Order Can Matter

Suppose two operations are called $$T_A$$ and $$T_B$$.

In general:

$$
T_B\circ T_A
\neq
T_A\circ T_B
$$



This property is called **noncommutativity**.

It means performing A and then B can produce a different outcome from performing B and then A.

Why?

Because the first transaction changes the state encountered by the second.



For NUT this can occur when:

* two trades use the same liquidity
* a large swap changes reserves
* a bonding-curve operation changes its next price
* concentrated liquidity moves across ranges
* an index operation changes component balances

The sequence of operations therefore matters.



This is one form of **path dependence**: the resulting state depends not only on what happened, but also on the order in which it happened.



***

### The NUT Opportunity Field

Different NUT markets can produce different executable prices at the same moment.

That creates possible routes between them.

For an executable direction from asset ii to asset jj, define:

$$
w_{ij}(\Omega_t,q)
$$

as the economic opportunity available for quantity qq under the current state.

This is a **state-dependent edge weight**.

“State-dependent” means its value changes when the market changes.

It must account for more than displayed prices.

A real NUT route may incur:

$$
C=
C_{\text{fees}}
+
C_{\text{gas}}
+
C_{\text{slippage}}
+
C_{\text{conversion}}
+
C_{\text{risk}}
$$

where:

* **fees** are charges imposed by the market mechanism
* **gas** is transaction execution cost
* **slippage** is deterioration in execution price caused by trade size
* **conversion cost** arises when intermediate assets must be exchanged
* **risk** captures economically relevant uncertainty such as latency or non-atomic execution



If a route begins with value $$V_{in}$$ and ends with $$V_{out}$$:

$$
\Pi =
V_{out}-V_{in}-C
$$

where $$\Pi$$ is net profit.



An arbitrage opportunity exists only when:

$$
\Pi>0
$$

A price difference alone is therefore insufficient.

The route must be profitable **after execution**.

### Backreaction

The interesting part is what happens next.

Suppose a NUT arbitrage route is profitable.



An arbitrageur executes it.

That transaction changes the pools.



Therefore:

$$
\Omega_t
\rightarrow
\Pi(\Omega_t)
\rightarrow
T
\rightarrow
\Omega_{t+1}
$$

and normally:

$$
\Pi(\Omega_{t+1})
\neq
\Pi(\Omega_t)
$$

This is **backreaction**.



Backreaction means an action changes the environment that produced the incentive for that action.

Arbitrage therefore tends to consume its own opportunity.

NUT markets continually create, expose, consume, and recreate these conditions.



***

### Graph State Is Not Graph Topology

There is one final distinction.

A **graph** is a mathematical structure consisting of objects called **nodes** connected by relationships called **edges**.



For NUT liquidity:

* assets can be represented as nodes
* pools or executable relationships can be represented as edges



Trading changes information carried by those edges:

* reserves
* prices
* liquidity
* opportunity

That changes the **state of the graph**.

But the connections themselves still exist.



By contrast, deploying a new NUT pool creates a new connection.

That changes the **topology** — the actual connectivity of the network.

Therefore:

$$
\text{graph-state change}
\neq
\text{topology change}
$$

A NUT swap changes the machine.

A new NUT market changes the structure of the machine.



### What We Can Measure

This model creates concrete research questions:

* Which NUT routes repeatedly become profitable?
* Which pools create the largest price differences?
* How quickly does arbitrage remove those differences?
* Which routes are most sensitive to trade size?
* Which operations exhibit strong path dependence?
* How does adding or removing NUT liquidity change routing?
* Can transactions themselves generate recurring NUT flow patterns?

These are empirical questions.

The Liquidity Machine is useful only where it helps describe or measure actual NUT behavior.

### Resources

For the mathematical concepts used on this page:

* **Wikipedia — Graph theory**
* **Wikipedia — Dynamical system**
* **Wikipedia — Function composition**
* **Wikipedia — Graph dynamical system**

These are general mathematical references. Their inclusion does not imply that NUT implements these mathematical frameworks directly.
