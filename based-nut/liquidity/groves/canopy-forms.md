# 🌿 Canopy Forms

A **Grove** tells us why liquidity structures belong together.



A **Canopy Form** tells us what shape those structures create when connected. It is the shape of liquidity when the Orchard is viewed from above.



That distinction matters.

* 🌾 **Crop** — what economic exposure exists.
* 🐝 **Guild** — what the liquidity is doing.
* 🌱 **Cultivation** — how the market is constructed.
* 🧬 **Heritage** — where it came from.
* 🌿 **Canopy** — how it connects.



{% hint style="info" %}
## 🌳 Grove vs. Canopy

**Grove = relationship.**

**Canopy = topology.**



A Reserve Grove can form a Hub-and-Spoke.\
An Arbitrage Guild can form a Ring.\
Weighted Grafts can form a Sunflower.

\
Several overlapping Groves can participate in the same Mesh.
{% endhint %}



***

## 🔭 From Microscope to Canopy

The Orchard can be viewed at several scales.



1. Micro to Macro Scales

* asset → pool → weighted structure → Grove → topology → Orchard

At microscopic scale, we ask:

> **What is this individual liquidity structure?**



2. Canopy Scales

* 🌿 Branch → 🌱 Graft → 🌸 Whorl

At Canopy scale, we ask:

> **What larger geometry emerges from many structures interacting?**



This is why Branch, Graft, and Whorl are not topology names.

They describe individual liquidity structures.

Canopy Forms describe the graph produced when those structures connect.

***

## ⚖️ Topology and Weight

Every liquidity structure has at least two important properties:

1. **Connectivity** — which assets and structures connect.
2. **Weight** — how economic influence is distributed inside them.



Connectivity determines the **Canopy**.

Weight changes the economic behavior inside that Canopy.



For example:

```
50 / 50
```

and:

```
90 / 10
```

can both be Branches.



Likewise:

```
20 / 40 / 40
```

and:

```
50 / 25 / 25
```

can both be Grafts.



Their topology may be identical while their:

* inventory exposure;
* price sensitivity;
* rebalancing pressure;
* arbitrage incentives;
* effective liquidity;

differ substantially.



{% hint style="info" %}
#### 🔬 Geometry and force

**Topology tells you where the connections are.**



**Weights tell you how strongly economic pressure acts through them.**
{% endhint %}



***

## ⭐ Hub-and-Spoke

A **Hub-and-Spoke** Canopy forms when many markets connect primarily through one common asset.

```
          A
          │
          │
B ────── NUT ────── C
          │
          │
          D
```

NUT is the hub.



The pair markets extending outward are the spokes.

This is the oldest recognizable topology in the Based Nut liquidity system.



### 🌿 Structural interpretation

Each individual pair is a **Branch**:

```
NUT / A
NUT / B
NUT / C
NUT / D
```



Together they create a shared-center graph.

The individual objects remain Branches.

**Hub-and-Spoke** describes the larger Canopy.



***

### 🧭 Economic behavior

A hub creates a common route between otherwise disconnected assets.



To move from `A` to `B`, liquidity can traverse:

```
A → NUT → B
```



This makes the hub important for:

* routing;
* common denomination;
* price transmission;
* liquidity concentration;
* arbitrage.



The stronger the hub's connectivity, the more Orchard paths depend on it.

***

## 🌻 Sunflower

The **Sunflower** is the characteristic Canopy of the Graft system.

Instead of many ordinary Branches sharing one vertex, several **ternary Grafts** share the same rootstock.



Each Graft has the form:

$${\mathrm{wNUT},s_i,s_j}$$



A collection of them creates:

```
                 A / B
                   │
                   │
C / D ────────── wNUT ────────── E / F
                   │
                   │
                 G / H
```

This drawing is shorthand.



Each apparent petal represents an entire three-token pool:

```
{wNUT, A, B}
{wNUT, C, D}
{wNUT, E, F}
{wNUT, G, H}
```

***

### 🌻 Hyperstar topology

An ordinary star consists of ordinary graph edges.

The Sunflower consists of **hyperedges**.



Every Graft shares the same distinguished vertex:

$$
r=\mathrm{wNUT}
$$

For a Sunflower containing Grafts:



$$
G_1,G_2,\ldots,G_n
$$

the common-root condition is:

$$
\mathrm{wNUT}
\in
\bigcap_{k=1}^{n} G_k
$$

The resulting structure is a **rooted hyperstar**.



The agricultural name is simpler:

> 🌻 **Sunflower**

***

### ⚖️ The initial Sunflower

The first experimental Sunflower uses five **Twin Grafts**.



Each begins with:

```
20% wNUT
40% Scion A
40% Scion B
```



The initial Scion pairs span several Crop Groves:

* ₿ Bitcoin / Reserve
* ◆ Ethereum / Reserve
* 💵 Settlement
* 🤖 AI / Agents
* 🧠 AI / Inference



The weights stay constant while the asset composition changes.

This makes the first Sunflower a controlled experiment in how different economic relationships behave under the same rooted geometry.

***

## 🔄 Ring

A **Ring** forms when liquidity closes into a cycle.

```
A ───────── B
│           │
│           │
D ───────── C
```

A route can begin at one asset, traverse several markets, and eventually return to the starting asset.



In graph terms, a Ring contains a cycle.



For vertices:

$$
v_0,v_1,\ldots,v_n
$$

a closed route satisfies:

$$
v_0=v_n
$$

with intermediate connections forming a valid liquidity path.

***

### 🥜 Ring I — NUT / SALT / USDC / PIPS



One Based Nut cycle already follows:

```
NUT
 ↓
SALT
 ↓
USDC
 ↓
PIPS
 ↓
NUT
```

or:

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

What makes this especially useful is that the cycle traverses different pricing mechanisms.

| Route       | Cultivation            |
| ----------- | ---------------------- |
| NUT → SALT  | Bonding Curve          |
| SALT → USDC | AMM                    |
| USDC → PIPS | reCLAMM                |
| PIPS → NUT  | Concentrated Liquidity |

One Ring therefore crosses several **Cultivation Groves**.

This is a direct example of Orchard **polyculture**.

***

### 🥜 Ring II — NUT / NUTINO / cbBTC

Another cycle can be represented as:

$$
\mathrm{NUT}
\rightarrow
\mathrm{NUTINO}
\rightarrow
\mathrm{cbBTC}
\rightarrow
\mathrm{NUT}
$$

Again, several markets combine into one closed economic path.

***

### ♻️ Why Rings matter

A cycle creates more than visual symmetry.



It can create:

* alternative routing paths;
* cross-market arbitrage;
* relative-price feedback;
* price propagation;
* rebalancing pressure;
* measurable state transitions.



If one edge of the Ring moves out of equilibrium, economic pressure can propagate around the cycle.



That makes Rings especially relevant to:

* 🛣️ Routing Guilds;
* ♻️ Arbitrage Guilds;
* 🌼 Price-Discovery Guilds;
* ✂️ Rebalancing Guilds.



***

## 🕸️ Mesh

A **Mesh** forms when a region has multiple independent paths between assets or liquidity structures.

```
A ───────── B
│ \       / │
│  \     /  │
│   \   /   │
│    \ /    │
│    / \    │
│   /   \   │
│  /     \  │
│ /       \ │
C ───────── D
```



Unlike Hub-and-Spoke topology, connectivity does not depend overwhelmingly on one center.

Unlike a simple Ring, several alternative routes can coexist.



***

### 🛣️ Route redundancy

Suppose there are two economically distinct routes from `A` to `D`:

```
A → B → D
```

and:

```
A → C → D
```

The network now has route redundancy.



If one market becomes:

* shallow;
* expensive;
* temporarily unavailable;
* badly priced;

another path may remain.



This is the core economic property of a Mesh.

***

## 🪢 Multiplex Is Not Automatically Mesh

The Orchard already contains examples where the same asset pair exists on more than one venue.



For example:

```
NUT / WETH — Venue A
NUT / WETH — Venue B
```

Mathematically, this creates **parallel edges**.



If two edges share the same endpoints:

$$
I(e_1)=I(e_2)
$$

while:

$$
e_1\neq e_2
$$

the graph is already a multigraph or multiplex structure.



But this alone does **not** produce a Mesh.



#### 🕸️ Parallel markets ≠ Mesh

Two venues connecting the same assets give the Orchard **multiplicity**.

A Mesh requires richer lateral connectivity and genuine alternative paths across several assets or structures.<br>

The Orchard therefore already has the ingredients for Mesh formation without needing to claim that every set of parallel pools is itself a Mesh.



***

## 🌳 Hierarchical

A **Hierarchical** Canopy appears when liquidity develops distinguishable layers of connectivity.

```
                   NUT
                /   |   \
               /    |    \
            WETH   SNUT   cbBTC
            / \      |      / \
           A   B     C     D   E
```



The system now contains:

1. a broad center;
2. secondary hubs;
3. peripheral markets.



NUT can remain the primary economic hub while assets such as:

* WETH;
* SNUT;
* cbBTC;



become local hubs for narrower regions of liquidity.

***

### 🌲 Hierarchy can emerge several ways

A secondary hub may arise because it has:

* many connected pools;
* deep liquidity;
* strong routing demand;
* important economic exposure;
* nested descendants;
* advantageous weights.



Hierarchy is therefore not necessarily designed in advance.



It can emerge from the state of the Orchard.

***

## 🧬 Hybrid

Real liquidity systems rarely remain perfect textbook examples of one topology.



The Orchard can simultaneously contain:

* ⭐ Hub-and-Spoke regions;
* 🌻 a Sunflower hyperstar;
* 🔄 several Rings;
* 🕸️ emerging Meshes;
* 🌳 hierarchical secondary hubs.



These forms can overlap.

```
                  NUT
              /    |    \
             /     |     \
          Ring   wNUT    WETH
                 / | \
                /  |  \
             Graft Graft Graft
                 \  |  /
                  Mesh
```



A single structure can therefore contribute to more than one Canopy Form.



For example, a Branch might simultaneously:

* act as a spoke in a Hub-and-Spoke;
* close a Ring;
* contribute a redundant path to a Mesh.



**Hybrid topology is not a separate primitive.**

It simply means several recognizable forms coexist in the same graph.



***

## 🌿 The Fractal Canopy



An unusual property of the Orchard is that similar forms appear at different scales.



At the broad level:

```
             NUT
          /   |   \
         /    |    \
        A     B     C
```



At the Graft level:

```
             wNUT
          /    |    \
         /     |     \
      Graft  Graft  Graft
```



NUT and wNUT are not topologically identical objects.



But because wNUT functions as the standardized Graft rootstock and maintains a 1:1 relationship with NUT, the smaller Graft system reproduces a similar shared-center pattern at another scale.



This gives the Orchard a **fractal-like structure**:

> similar connectivity patterns recurring at different levels of abstraction.



***

## 🌳 Canopy Forms Across Grove Classes



Canopy and Grove classification are independent axes.

The same topology can appear under entirely different semantic projections.



| Grove              | Possible Canopy                |
| ------------------ | ------------------------------ |
| ₿ Reserve Grove    | Hub-and-Spoke, Sunflower, Ring |
| 🤖 Compute Grove   | Sunflower, Ring, Mesh          |
| 🛣️ Routing Guild  | Ring, Mesh, Hierarchical       |
| ♻️ Arbitrage Guild | Ring, Mesh                     |
| ⚖️ Weighted Grove  | Sunflower, Hub-and-Spoke       |
| 🧬 NUT Lineage     | Hierarchical, Hub-and-Spoke    |

Likewise, one Canopy may contain members from several Grove classes.



A Sunflower can simultaneously contain:

* Reserve Grafts;
* Settlement Grafts;
* Compute Grafts;
* Weighted Grafts;
* Cross-Pollination Guild members.



The topology does not erase those semantic relationships.

It reveals how they connect.

***

## ⚖️ Weights Change the Canopy's Economics

Two graphs can have identical topology but behave differently because their pools use different weights.



Consider two identical Hub-and-Spoke graphs.



#### Canopy A

```
Every Branch: 50 / 50
```



#### Canopy B

```
Every Branch: 90 / 10
```



Their connectivity is identical.

Their economic response is not.



Likewise, two Sunflowers could share exactly the same Graft layout while using different Graft geometries:

```
Sunflower A
20 / 40 / 40
```

```
Sunflower B
50 / 25 / 25
```



Differences could emerge in:

* capital concentration;
* inventory risk;
* price impact;
* arbitrage frequency;
* rebalancing;
* rootstock exposure.



This is why weights are a **lens on topology**, not a substitute for topology.

***

## 🔄 A Living Canopy

Canopy Forms can change as Orchard state changes.



A new market can:

* close a Ring;
* connect two previously separate regions;
* create a secondary hub;
* add route redundancy;
* turn a star-like graph into a Mesh;
* connect two Crop Groves;
* create a new arbitrage path.



A removed or depleted market can do the reverse.



If the Orchard at time `t` is:

$$
\mathcal{O}_t
$$

then an economic or deployment event can produce:

$$
\mathcal{O}t
\longrightarrow
\mathcal{O}{t+1}
$$



The topology of those two states need not be identical.

Therefore:

> **The Canopy itself is part of Orchard state.**

***

## 🧭 Reading a Canopy

When examining any region of the Orchard, ask:

#### ⭐ Is there one dominant center?

→ **Hub-and-Spoke**



#### 🌻 Do multiple rooted Grafts share wNUT?

→ **Sunflower**



#### 🔄 Does a route close back onto itself?

→ **Ring**



#### 🕸️ Are there several independent routes between regions?

→ **Mesh**



#### 🌳 Are there primary, secondary, and peripheral hubs?

→ **Hierarchical**



#### 🧬 Are several of these simultaneously true?

→ **Hybrid**



***

## 🌿 Current Orchard Forms

At the current stage of the Orchard:

#### ⭐ Hub-and-Spoke

**Established.**

NUT already acts as the common hub across many pair markets.



#### 🌻 Sunflower

**Established as the Graft architecture.**

Multiple weighted Grafts share wNUT as common rootstock.



#### 🔄 Ring

**Already present.**

At least two economically meaningful cycles can be identified across existing liquidity structures.



#### 🌳 Hierarchical

**Already visible.**

NUT acts as the broad center while assets such as WETH, SNUT, and cbBTC can serve as secondary connectivity points.



#### 🕸️ Mesh

**Emerging.**

Parallel markets and alternative connections already provide the ingredients, but multiplicity should not be mislabeled as a mature Mesh before genuine lateral route redundancy develops.



#### 🧬 Hybrid

**Already the global condition.**

The Orchard contains several topology forms simultaneously.



***

## 🥜 The Canopy Rule

#### 🌿 One word, one concept

**Branch, Graft, and Whorl describe individual liquidity structures.**

**Groves describe relationships among those structures.**

**Canopy Forms describe the geometry produced when they connect.**

**Weights describe the economic balance inside that geometry.**

**State determines which forms exist right now.**<br>

The Canopy is the Orchard viewed from above.
