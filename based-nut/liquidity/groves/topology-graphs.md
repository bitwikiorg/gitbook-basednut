---
icon: diagram-project
---

# Topology Graphs

## 🕸️ Liquidity Topology Graphs & Hypergraphs

**The mathematical structure beneath the Orchard.**

<figure><img src="../../.gitbook/assets/9f9cde14-a7d8-4120-9186-b78158e956ad.png" alt=""><figcaption></figcaption></figure>

The Orchard can be read as a liquidity graph:

```
asset             → vertex
Branch            → edge
Graft             → rooted ternary hyperedge
Whorl             → multi-asset hyperedge
route             → path
Canopy            → topology
market condition  → state
```



The graph asks:

> **What is connected to what?**



The Canopy asks:

> **What structure emerges from those connections?**



The deeper question is:

> **What can actually move through that structure, in what quantity, at what cost, and under what state?**



That is where a liquidity graph becomes an economic system.

***

## 📐 The Orchard as a Stateful Hypergraph

A compact representation of the Orchard is:

$$
\mathcal{O}_t
=
\left(
V,
E,
I,
\lambda,
r,
\Sigma_t
\right)
$$

where:

* **V** — assets;
* **E** — distinct liquidity structures;
* **I(e)** — the assets participating in structure `e`;
* **λ(e)** — mechanism, venue, weights, fees, lineage, and other metadata;
* **r = wNUT** — distinguished Graft rootstock;
* **Σₜ** — mutable economic state.

This is richer than a simple graph.

It must represent:

* ordinary pairwise markets;
* multi-asset pools;
* several markets connecting the same assets;
* different pricing mechanisms;
* nested liquidity claims;
* changing execution conditions.

The Orchard is therefore best understood as a:

> **stateful, typed, multiplex liquidity hypergraph.**

***

## 🔗 Branches as Edges

For a normal two-token pool:

```
NUT / WETH
```

the graph representation is straightforward:

```
NUT ───────── WETH
```



Formally:

$$
B_{ij}
=
\{a_i,a_j\}
$$



The two assets are vertices.

The pool is the edge.

But the edge is not merely a statement that the assets are related.



It carries state:

* reserves;
* liquidity;
* fees;
* price;
* active ranges;
* invariant;
* volume;
* LP positions;
* execution conditions.

So even the simplest Orchard edge is a **stateful market object**.

***

## 🪢 Multiplex Liquidity

Two assets can have several independent markets.

For example:

```
             V2
NUT ───────────────── WETH

             V3
NUT ───────────────── WETH
```

Both markets touch the same assets:

$$
I(e_1)
=
I(e_2)
$$

but the pools themselves remain distinct:

$$
e_1
\neq
e_2
$$



They may have different:

* liquidity;
* fees;
* invariants;
* price ranges;
* LP ownership;
* execution prices;
* market state.



This is why the Orchard cannot collapse every asset pair into one abstract connection.

It is **multiplex**.



Multiple independent economic layers can occupy the same apparent place in the graph.



#### 🪢 Same endpoints, different markets

A graph of asset pairs says:

**NUT connects to WETH.**

A multiplex liquidity graph preserves the stronger statement:

**NUT connects to WETH through several independent economic state machines.**

***

## 🌱 Grafts as Rooted Hyperedges

A Graft cannot be represented faithfully as three unrelated pairwise markets.

Its structure is:

$$
G_{ij}
=
\{\mathrm{wNUT},s_i,s_j\}
$$

For example:

```
{wNUT, cbBTC, tBTC}
```

is one shared market.

Conceptually:

```
             cbBTC
                \
                 \
                POOL
                 /
                /
              tBTC
                │
                │
               wNUT
```

The three assets share:

* one pool;
* one invariant;
* one liquidity state;
* one LP system;
* one set of weights.

A Graft is therefore a **ternary hyperedge**, not three independent Branches.

***

## 🌸 Whorls as General Hyperedges

The same principle applies to larger pools.

Suppose a four-asset Whorl contains:

```
NUT
SNUT
cbETH
cbBTC
```

It would be misleading to replace that one pool with six unrelated pairwise markets.

Those apparent pairwise relationships all mutate the same shared pool state.

The correct abstraction is one hyperedge:

$$
W
=
\{
\mathrm{NUT},
\mathrm{SNUT},
\mathrm{cbETH},
\mathrm{cbBTC}
\}
$$

Conceptually:

```
                NUT
                 │
                 │
SNUT ────────── POOL ────────── cbETH
                 │
                 │
               cbBTC
```

One pool.

Four assets.

One shared state.

***

## 🧬 Shared State Is the Important Part

The reason hyperedges matter is not merely that they contain more vertices.

It is that the assets participate in the **same economic state machine**.

A multi-asset pool may share:

* balances;
* weights;
* fees;
* invariant;
* LP supply;
* price relationships.

If one trade mutates the pool, the economic conditions relating several assets can change simultaneously.

That coupling disappears if the pool is mentally decomposed into unrelated pair markets.



#### 🕸️ Hyperedge principle

A multi-asset pool is not merely many pairwise exchange possibilities.

It is **one shared state from which several exchange possibilities emerge**.



***

## ⚖️ Two Different Kinds of Weight

The word **weight** appears in two different layers of the system.

They should not be confused.

### 🌱 Pool Weight

Inside a weighted Graft:

```
20% wNUT
40% cbBTC
40% tBTC
```

the weights are part of the market's internal geometry.

For example:

$$
w_{\mathrm{wNUT}}
=
0.20
$$

$$
w_{\mathrm{cbBTC}}
=
w_{\mathrm{tBTC}}
=
0.40
$$

These weights affect the economics of the pool itself.

***

### 🛣️ Graph Weight

A router may also assign a **cost** to traversing an edge or hyperedge.



That cost may depend on:

* fees;
* slippage;
* gas;
* price impact;
* available liquidity;
* execution probability;
* route complexity.



#### ⚖️ Pool weight ≠ graph weight

**Pool weight** describes economic composition inside a market.

**Graph weight** describes the cost or desirability of traversing a path through the network.

***

## 🧭 Paths

Once liquidity structures connect assets, value can move through paths.



For example:

```
SNUT
 ↓
NUT
 ↓
cbBTC
```

or:

```
SALT
 ↓
USDC
 ↓
PIPS
 ↓
NUT
```



A path can be represented as an alternating sequence:

```
Asset A
   ↓
Pool 1
   ↓
Asset B
   ↓
Pool 2
   ↓
Asset C
```



The existence of a path means two assets are structurally reachable even when they share no direct pool.

But structural reachability is only the beginning.

***

## 💧 Reachability Is Not Executability

Suppose:

```
A ───── B ───── C
```

A graph theorist can say:

> `A` is connected to `C`.



An economic system must ask:

> **Can $10 move from A to C?**

and separately:

> **Can $100,000 move from A to C?**



Those can have different answers.



A route may exist structurally while being economically useless because of:

* shallow liquidity;
* excessive price impact;
* inactive concentrated liquidity;
* high fees;
* gas costs;
* current pool imbalance.



A useful notion of reachability therefore depends on:

* source asset;
* destination asset;
* trade size;
* time;
* acceptable execution cost.



Conceptually:

$$
\mathrm{Reachable}
\left(
A,
B;
q,
t,
\varepsilon
\right)
$$

where:

* `q` = trade quantity;
* `t` = current state;
* `ε` = maximum acceptable execution cost.



This leads to a stronger result:

> **Liquidity topology is trade-size dependent.**

A network can be connected for a $10 trade and effectively disconnected for a $1,000,000 trade.

***

## ⚖️ Structure Is Not Capacity

Consider two networks with identical topology:

```
A ───── B ───── C
```



The first may support only:

```
$20
```

before execution becomes unusable.



The second may support:

```
$20,000,000
```

The graph shape is identical. Its economic capacity is not.



So:

```
structure
   +
capacity
   =
usable liquidity network
```

This is why raw connectivity is insufficient.

And raw TVL is insufficient in the opposite direction.



A market can contain substantial capital while contributing little useful connectivity to the broader system.

***

## 🛣️ Executable Topology

This suggests two different maps of the same Orchard.



### 🧱 Contract Topology

What markets technically exist?

```
deployed contracts
      ↓
assets + pools
      ↓
structural graph
```



### ⚡ Executable Topology

What routes are economically usable now?

```
structural graph
      +
current state
      +
trade size
      +
execution constraints
      ↓
executable graph
```

The contract topology can remain unchanged while the executable topology changes dramatically.



For example:

* liquidity leaves a pool;
* a concentrated range becomes inactive;
* fees increase;
* prices diverge;
* a route becomes too expensive;
* another venue suddenly becomes preferable.



The contracts still exist.

The usable graph has changed.

***

## 🔄 Routing as State Transition

A route is not merely a line drawn through a graph.

It is an ordered sequence of state-changing executions.



For a path:

$$
P
=
(e_1,e_2,\ldots,e_k)
$$

execution can be represented as:

$$
\Sigma_0
\xrightarrow{e_1}
\Sigma_1
\xrightarrow{e_2}
\Sigma_2
\longrightarrow
\cdots
\xrightarrow{e_k}
\Sigma_k
$$

Each operation changes the state encountered by later operations.



That matters especially when:

* trade size is large;
* the same pool is touched more than once;
* several actions occur atomically;
* a route closes into a cycle;
* several agents compete for the same state.



Routing is therefore a **state-transition problem**, not merely a graph-search problem.

***

## 🔄 Cycles Become Economic Objects

The Polyforest contains a useful example:

$$
\mathrm{NUT}
\rightarrow
\mathrm{SALT}
\rightarrow
\mathrm{USDC}
\rightarrow
\mathrm{PIPS}
\rightarrow
\mathrm{NUT}
$$

Topologically, this is a Ring.

Economically, it is more interesting.



A cycle becomes an arbitrage opportunity only when its full executable path returns more value than it consumes.



Conceptually:

$$
V_{\mathrm{out}}
>
V_{\mathrm{in}}
$$



after accounting for:

* fees;
* slippage;
* gas;
* price impact;
* state changes during execution.



This distinction matters:

> **A cycle is topology. Arbitrage is a state-dependent property of that cycle.**



The Ring can exist permanently.

The arbitrage may exist for milliseconds.

***

## 🌉 Bridges and Bottlenecks

Some liquidity structures matter more than their TVL suggests.

Suppose two dense regions connect through one market:

```
CLUSTER A
    │
    │
  BRIDGE
    │
    │
CLUSTER B
```

If removing that market disconnects the graph, it is a structural **bridge**.

But liquidity introduces another possibility.

Several alternative routes may technically exist while only one carries meaningful economic capacity.

That market is an **economic bridge** even if it is not a strict graph-theoretic bridge.

***

### 🪓 Cut Sets

Sometimes no single market is critical.

Instead, a small set of markets collectively holds the network together.

```
region A
  │   │
 e₁   e₂
  │   │
region B
```

Removing both may disconnect the regions.

This set acts as a **cut**.

For protocol design, the practical question becomes:

> **How many independent markets must fail before this region becomes economically unreachable?**



That is a stronger measure of resilience than counting pools.

***

## 🚧 Bottlenecks

A bridge may remain available but become too shallow for meaningful routing.

```
DEEP REGION
     │
     │
 $800 pool
     │
     │
DEEP REGION
```

The topology says the network is connected.

The capacity says otherwise.



A bottleneck is therefore a point where **available path capacity becomes constrained**.



This produces a useful distinction:

* **structural resilience** — alternative connections exist;
* **economic resilience** — alternative connections have enough capacity to matter.

***

## 🎯 Centrality

Once the Orchard becomes large, not every asset or market is equally important.

Graph theory provides several useful lenses.



### 🔗 Degree

How many structures touch a vertex?

An asset with many direct markets has high degree.

NUT naturally tends toward this role.

***

### 🛣️ Betweenness

How often does an asset or market sit on useful paths between other regions?

An asset can have relatively few direct pools yet become extremely important because many routes pass through it.

***

### 💧 Liquidity-Weighted Centrality

Pure topology still ignores economic capacity.



A more useful Orchard metric would weight importance by properties such as:

* executable liquidity;
* route volume;
* slippage;
* trade size;
* active depth.



This produces an important distinction:

> **The most connected asset is not necessarily the most economically important routing asset.**



Centrality depends on what the network is being used to do.

***

## 🧬 Recursive Liquidity

Some Orchard assets represent claims on other liquidity structures.



Consider:

```
Asset A + Asset B
        ↓
       Pool
        ↓
     LP token
        ↓
   second market
        ↓
      WETH
```

The LP token is itself a vertex in another liquidity graph.

But economically it represents an underlying pool.

This creates **second-order liquidity**.



For example:

```
SNUT liquidity
      ↓
   SNUT-LP
      ↓
SNUT-LP / WETH
```

The market graph alone no longer tells the entire story.

***

## 🕸️ Market Graph vs. Dependency Graph

Recursive liquidity introduces two overlapping structures.



### 🛣️ Market Graph

> What can trade against what?

{% code overflow="wrap" %}
```
LP token ───── WETH
```
{% endcode %}



### 🧬 Dependency Graph

> What derives its economic state from what?

```
Asset A
   \
    Pool → LP token
   /
Asset B
```

A single asset can therefore participate in:

* one graph through tradability;
* another graph through economic dependency.



This becomes even more important with:

* LP tokens;
* vault shares;
* wrappers;
* nested assets;
* tokenized positions.



The future Orchard may need to model both graphs simultaneously.

***

## ⏱️ The Graph Changes in Two Ways

There are two fundamentally different kinds of change.



### 🧱 Structural Change

The graph itself changes.



Examples:

* a pool is deployed;
* a Graft is planted;
* a pool is removed;
* a market migrates.



Formally:

$$
E_t
\neq
E_{t+1}
$$

***

### 💧 Economic Change

The structures remain, but their usable state changes.



Examples:

* liquidity moves;
* weights rebalance;
* prices change;
* ranges become inactive;
* a bottleneck appears;
* an arbitrage path opens or closes.



The pool set may remain identical:

$$
E_t
=
E_{t+1}
$$

while:

$$
\Sigma_t
\neq
\Sigma_{t+1}
$$

and therefore the executable topology changes.



This means the Orchard has both:

> **structural topology**

and:

> **state-dependent executable topology**

***

## 🤖 Why Machines Care About the Second One

Humans often look at a liquidity graph as a diagram.

Machines can evaluate it as a continuously changing state space.



A router or autonomous agent does not merely ask:

> Is there a path?



It can ask:

* What path exists now?
* For what size?
* At what cost?
* Through which mechanisms?
* What state will execution create?
* What route becomes available after that transition?
* What other agent is likely to act first?



This is the point where the liquidity graph begins to approach something larger than market visualization.

```
current state
      ↓
possible actions
      ↓
possible next states
      ↓
new possible actions
      ↓
state space
```

The graph does not merely describe where value **is**.

It begins to describe where value **can go next**.

***

## 🌳 The Orchard View

At the simplest level:

```
assets
+
liquidity structures
=
liquidity graph
```

Add topology:

```
liquidity graph
+
structural arrangement
=
Canopy
```

Add mutable economic state:

```
Canopy
+
Σₜ
=
stateful Orchard
```

Add execution constraints:

```
stateful Orchard
+
trade size
+
fees
+
slippage
+
capacity
=
executable topology
```

And add autonomous actors:

```
executable topology
+
agents
+
recursive state transitions
=
machine-accessible economic state space
```

NUT is an important vertex.

wNUT is the distinguished Graft rootstock.

Branches, Grafts, and Whorls create the liquidity structures.

Groves reveal meaningful projections.



The Canopy reveals their shape.

But the deepest object is the changing set of **economically possible transitions** between states.



#### 🕸️ The advanced view

**The contract graph shows what exists.**

**The liquidity graph shows what connects.**

**The Canopy shows what shape emerges.**

**The state machine shows what changes.**

**Executable topology shows what can actually happen now.**



That executable topology is the terrain autonomous economic systems will navigate.
