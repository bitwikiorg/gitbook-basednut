# 🫗 NUT Liquidity Graphs

{% hint style="danger" %}
### **WARNING: YOU ARE READING** HYPER ADVANCED NUT RESEARCH

We have exhausted the practical explanations and are now investigating what happens when very smart people are left alone with **1 NUT** for too long. The whitepaper needed more symbols. Advanced theory needed more equations. Apparently neither was enough. Welcome to the part where we give the NUT a research PhD program.
{% endhint %}

NUT does not exist in one isolated market.

It is economically connected to other assets reachable through liquidity routes

These relationships can be represented as a **liquidity graph**.



A graph is a mathematical structure made from:

* **nodes** — the objects being connected
* **edges** — the relationships connecting them
*

For NUT liquidity, assets can be nodes and markets can be edges.



A simple NUT/WETH pool becomes:

```
NUT ───── WETH
```



Several NUT markets produce a larger graph:

```
             WETH
               │
               │
AERO ──────── NUT ──────── cbBTC
               │
               │
             SNUT
```



The graph answers a basic question:

> **What is economically connected to NUT?**



***

### A Pool Is More Than an Edge

The line:

```
NUT ───── WETH
```

only tells us that a relationship exists.



A real liquidity pool also contains economic state:

* reserves
* liquidity
* fees
* price
* curve
* trade capacity
* execution conditions



We can therefore represent the NUT liquidity graph as:

$$
G_t=(V,E,W_t)
$$

where:

* $$V$$ is the set of assets
* $$E$$ is the set of economic connections
* $$W_t$$ is the state carried by those connections at time $$t$$

The subscript $$t$$ matters because liquidity relationships change over time.



The NUT/WETH connection may still exist tomorrow while its:

* reserves
* price
* depth
* active range

are completely different.



***

### Weighted NUT Graphs

A **weighted graph** is a graph in which a numerical value, called a weight, is attached to an edge.

In a road network, a weight might represent distance.



In a NUT liquidity graph, a weight could represent:

* executable price
* fee
* liquidity depth
* slippage
* route capacity
* net economic opportunity



However, NUT markets are nonlinear.

A route may be inexpensive for a tiny trade but expensive for a large trade.



A more useful NUT edge weight is therefore:

$$
w_{ij}(\Omega_t,q)
$$

where:

* $$i$$ is the input asset
* $$j$$ is the output asset
* $$\Omega_t$$ is current economic state
* $$q$$ is trade size

The edge weight depends on both **state and quantity**.



### Direction Matters

A pool may connect NUT and WETH in both directions:

```
NUT ⇄ WETH
```

but the two executions are not identical.



We should distinguish:

$$
NUT\rightarrow WETH
$$

from:

$$
WETH\rightarrow NUT
$$



A **directed graph** is a graph whose edges have direction.



Directed representation is useful for NUT because each direction can have a different:

* input quantity
* output quantity
* slippage
* fee consequence
* economic opportunity

So an undirected connection may represent the existence of a pool, while directed edges represent actual execution.



***

### NUT Routes

A **route** is an ordered sequence of economic connections.



For example:

```
NUT → AERO → WETH
```

is a two-edge route.



A longer route might be:

```
NUT → child token → external asset → NUT
```

We can write a route as:

$$
P=
(v_0,e_1,v_1,e_2,\ldots,e_n,v_n)
$$

where:

* $$v$$ represents assets
* $$e$$ represents executable mechanisms



The economic question is:

> **Which executable route produces the best result for a specified quantity?**



For input quantity $$q$$:

$$
\arg\max_P \Pi_P(q)
$$

where:

* $$P^*$$ means the best route under the chosen objective
* $$\Pi_P(q)$$ is the net economic result of route $$P$$

The best route can change with trade size.



***

### NUT Cycles

A **cycle** is a route that eventually returns to its starting point.



For example:

```
NUT → A → B → NUT
```



If the route begins with quantity q0q\_0 of NUT and returns:

$$
q_1>q_0
$$

after all execution costs, the cycle contains an arbitrage opportunity.



More generally:

$$
\Pi_P>0
$$

must hold after:

* fees
* gas
* slippage
* intermediate conversion
* applicable taxes
* relevant execution risk



This means an arbitrage cycle is not simply a geometric loop in the graph.

It is a **profitable executable loop under a particular state and quantity**.



***

### Cycles Are State-Dependent

Suppose:

```
NUT → AERO → WETH → NUT
```

is profitable.



Execution changes the pools involved.



The same cycle may immediately become:

* less profitable
* unprofitable
* profitable in the opposite direction

The topology has not changed.

The edge states have.



Therefore:

> **A route belongs to the graph. Profitability belongs to the graph's state.**



***

### Multi-Asset Relationships

Ordinary graphs are naturally pairwise.

An edge connects two nodes.



But some NUT structures relate more than two assets simultaneously.



Consider an index or multi-asset pool containing:

$$
{NUT,SNUT,cbETH,cbBTC}
$$



Representing this only as many pairwise connections can obscure an important fact:

> all four assets participate in one shared economic mechanism.

This motivates a **hypergraph**.



***

### What Is a Hypergraph?

A **hypergraph** generalizes an ordinary graph.

In an ordinary graph, one edge connects two nodes.

In a hypergraph, a **hyperedge** can connect any number of nodes.



For example:

$$
e=
{NUT,SNUT,cbETH,cbBTC}
$$

can represent one four-asset relationship.



A hypergraph can be written:

$$
H=(V,\mathcal E)
$$

where:

* $$V$$ is the set of assets
* $$\mathcal E$$ is the set of hyperedges



A normal two-token pool is still representable.

It is simply a hyperedge containing two assets.



***

### Why Hypergraphs May Matter for NUT

Suppose a four-asset structure is converted into six pairwise relationships.

That projection may hide:

* shared reserves
* common weights
* joint constraints
* common rebalancing rules
* shared contract risk
* simultaneous dependencies

Hypergraphs preserve the fact that several assets participate in one mechanism.



This may make them useful for representing:

* pNUT
* weighted multi-asset pools
* indexes
* multi-asset vaults
* future NUT Grafts and Whorls

But hypergraph theory should only be used where the pairwise graph actually loses economically relevant information.



If an ordinary graph explains the system adequately, it is preferable because it is simpler.



***

### Graph Projection

A **projection** converts a more complex representation into a simpler one.



For example, a four-asset hyperedge:

$$
{A,B,C,D}
$$

can be projected into pairwise edges:

```
A ─ B
│ \ │
│  \│
C ─ D
```

The projection is easier to route through computationally.



But it may no longer show that all edges came from one shared mechanism.

This gives us an empirical question:

> **What information about NUT relationships disappears when hyperedges are reduced to ordinary edges?**
>
>

***

### Routing Centrality

Some NUT markets may become structurally important because many routes depend on them.

**Centrality** is a family of graph measures used to describe how important or structurally positioned a node or edge is within a network.



For NUT, ordinary graph centrality may be insufficient.

A venue with many connections may have almost no usable liquidity.

A venue with fewer connections may carry most executable flow.



A NUT-specific routing centrality could instead measure:

$$
\frac{
\text{economically relevant routed flow through }i
}{
\text{total measured routed flow}
}
$$

This could be calculated from:

* observed transactions
* arbitrage routes
* routing simulations
* standardized trade-size queries

The exact methodology must be specified before comparing venues.



***

### State Change vs Topology Change

The graph makes an important distinction visible.

A swap can change:

* reserves
* prices
* liquidity
* edge weights

without adding or removing any relationship.



That is a **graph-state change**.

Deploying a new NUT pool creates a new economic relationship.



That is a **topology change**.

$$
\Delta G_{\text{state}}
\neq
\Delta G_{\text{topology}}
$$



For NUT:

> **Trading changes the condition of existing relationships. Deployment changes what relationships exist.**

***

### NUT as the Rooted Graph

Because NUT is the conserved root asset, we can also study the graph specifically from NUT outward.

Questions include:

* What assets are one edge away from NUT?
* What assets require two or more transitions?
* Which NUT markets act as routing hubs?
* Which child assets reconnect to NUT?
* Which multi-asset structures share NUT ancestry?
* Which routes disappear if one NUT market loses liquidity?



This turns the generic liquidity graph into a **rooted NUT liquidity graph**.

NUT is not merely another node being mapped.

It is the reference node from which the surrounding economic structure is being studied.

### Resources

* Wikipedia — Graph theory
* Wikipedia — Directed graph
* Wikipedia — Weighted graph
* Wikipedia — Hypergraph

These are general mathematical concepts. Their use here describes NUT's economic relationships; it does not imply that deployed NUT contracts themselves implement a graph database or graph algorithm.
