---
description: From individual pools to a living liquidity system.
---

# 🌲 Groves

The **Orchard** is the complete Based Nut liquidity graph and the groves are different collections of similar liquidity graphs.

<figure><img src="../../.gitbook/assets/image (18).png" alt="" width="563"><figcaption></figcaption></figure>



At the smallest scale are individual assets and pools.

Zoom outward and those pools form relationships: by economic exposure, function, market mechanism, lineage, routing, and topology.



The tree language gives each scale a distinct name.

{% hint style="info" %}
## 🌳 The framework at a glance

**Assets → Liquidity Structures → Groves → Canopy → Orchard**

* **Structure** tells you what kind of pool it is.
* **Weights** tell you how influence is distributed inside it.
* **Groves** tell you why structures belong together.
* **Canopy Forms** tell you what shape their connections create.
* **State** tells you what the system looks like now.
{% endhint %}



***

### 🔬 From Pool to Orchard

The framework becomes easiest to understand by changing scale.



#### 🥜 Assets

The vertices of the liquidity graph.

* **NUT** — underlying root asset.
* **wNUT** — standardized Graft rootstock.
* **Scion** — an asset attached through a Graft.
* Other Orchard assets may participate directly in Branches, Whorls, curves, wrappers, or other venues.



#### 🌿 Liquidity Structures

Pools are classified first by their **asset structure**.

<table><thead><tr><th width="166">Orchard term</th><th width="194">Assets in the pool</th><th>Structure</th></tr></thead><tbody><tr><td>🌿 <strong>Branch</strong></td><td><strong>2 tokens</strong></td><td>ordinary liquidity edge</td></tr><tr><td>🌱 <strong>Graft</strong></td><td><strong>3 tokens</strong></td><td>rooted ternary hyperedge</td></tr><tr><td>🌸 <strong>Whorl</strong></td><td><strong>4+ tokens</strong></td><td>multi-asset hyperedge</td></tr></tbody></table>

This gives every pool one structural class.



{% hint style="info" %}
## ⚖️ Structure ≠ Weight

**Arity tells you what the pool is. Weights tell you how influence is distributed inside it.**

A `20 / 40 / 40` pool is not automatically a Graft.

It becomes a Graft only when its three assets are:

**wNUT + Scion A + Scion B**
{% endhint %}



***

## 🌿 Branch

A **Branch** is a two-token liquidity pool.

$$
B_{ij} = \{a_i, a_j\}
$$

Examples:

* NUT / WETH
* NUT / SNUT
* SALT / USDC
* PIPS / NUT

A Branch may use any supported two-asset market mechanism.



Its weights can vary:

* `50 / 50`
* `80 / 20`
* concentrated liquidity rather than fixed weights
* another two-asset invariant



It remains a **Branch** because it connects exactly two assets.



#### 🌿 Parallel Branches

The same pair can exist on multiple venues.

For example:

* NUT / WETH — Uniswap V2
* NUT / WETH — Uniswap V3



These share the same assets but are **different liquidity edges** because their venue, mechanism, fee structure, liquidity state, and market behavior differ.



This is part of what makes the Orchard **multiplex** rather than a simple graph.

***

## 🌱 Graft

A **Graft** is exactly one rooted three-token liquidity pool.

$$
G_{ij} = \{\mathrm{wNUT}, s_i, s_j\}
$$

where:

* **wNUT** = common rootstock
* **sᵢ** = Scion A
* **sⱼ** = Scion B



Visually:

```
       Scion A
          \
           \
          wNUT
           /
          /
       Scion B
```



The definition is intentionally strict.

A Graft must contain:

1. exactly three assets;
2. wNUT as the common rootstock;
3. two Scions.



Therefore:

* a 2-token pool is **not** a Graft;
* an unrooted 3-token pool is **not** a Graft;
* a 4-token pool is **not** a Graft.



#### ⚖️ Graft Weights

Weights describe the internal economic geometry of the Graft.

For example, the **Twin Graft** uses:

```
20% wNUT
40% Scion A
40% Scion B
```



But all of these could still be Grafts:

```
33 / 33 / 33
20 / 40 / 40
50 / 25 / 25
70 / 20 / 10
```

provided the structure remains:

```
wNUT + Scion A + Scion B
```



The rootstock defines the **Graft**.

The weights define its **balance**.



***

## 🌸 Whorl

A **Whorl** is any multi-asset pool containing three or more assets that is **not** a Graft.

$$
W = \{a_1, a_2, \ldots, a_n\}, \qquad n \geq 3
$$



Botanical whorls naturally vary in number, so the term remains useful across different pool sizes.

A Whorl may therefore be:

* **3-merous** — three assets;
* **4-merous** — four assets;
* **5-merous** — five assets;
* or larger.



#### 🧬 pNUT as an Heirloom Whorl

The historical pNUT weighted pool is a useful example.

It contains four assets at equal weight:

```
25 / 25 / 25 / 25
```

NUT participates as one member of the pool rather than wNUT acting as a distinguished rootstock.

It is therefore:

* structurally a **Whorl**;
* mechanistically **Weighted**;
* historically an **Heirloom**.

pNUT predates the Graft architecture without needing to be retroactively forced into it.

***

## ⚖️ Weights as the Economic Lens



Structure tells us **what connects**.

Weights tell us **how strongly each component participates**.

The same structural object can exhibit very different economic behavior depending on its weights.



#### 🌿 Branch

```
50 / 50
```

and:

```
90 / 10
```

are both Branches.



#### 🌱 Graft

```
20 / 40 / 40
```

and:

```
50 / 25 / 25
```

can both be Grafts.



#### 🌸 Whorl

```
25 / 25 / 25 / 25
```

and:

```
70 / 10 / 10 / 10
```

can both be four-asset Whorls.



Weights influence:

* inventory exposure;
* rebalancing pressure;
* price sensitivity;
* arbitrage incentives;
* effective liquidity;
* capital concentration;
* asset dominance;
* routing behavior.



{% hint style="info" %}
## 🔬 Two lenses

The two dimensions should remain separate.



**Structure:** Branch → Graft → Whorl

**Weight:** how economic influence is distributed inside that structure
{% endhint %}



***

## 🌳 What Is a Grove?

A **Grove** is a meaningful projection of related liquidity structures within the Orchard. In other words, it is a collection of liquidity pools that serve a common purpose or share a common theme.&#x20;



It may contain:

* Branches;
* Grafts;
* Whorls;
* several venues for the same assets;
* structures already belonging to other Groves.



A Grove is **not** another pool primitive.



It is a way of asking:

> **Which parts of the Orchard belong together under this relationship?**



A Grove can be economically, functionally, mechanistically, or historically coherent.



More formally:

#### 📐 Grove projection

$$
\mathcal{G}_{\phi,t}
=
\mathcal{O}_t
\left[
\left\{
e \in E
\;\middle|\;
\phi(e,\lambda(e),\Sigma_t)=1
\right\}
\right]
$$

#### The rule **φ** selects the structures that belong to the Grove under a particular lens.



The practical meaning is simpler:

> **Change the question and you reveal a different Grove.**



## 🔀 One Structure, Several Groves

Groves are **overlapping projections**, not mutually exclusive folders.



Consider a hypothetical Graft containing:

```
20% wNUT
40% AI Scion
40% BTC Scion
```



That single market could be described through several lenses:

#### 🌱 Structure

* **Graft**

#### 🌾 Crop

* **Compute Grove**
* **Reserve Grove**

#### 🐝 Guild

* **Cross-Pollination Guild**
* **Routing Guild**
* **Price-Discovery Guild**

#### 🌱 Cultivation

* **Weighted Grove**

#### 🧬 Heritage

* whatever lineage is actually applicable



Think of groves as ways of tagging and organizing collections of liquidity pools.

***

## 🌿 Canopy Forms

A Grove tells us **why structures belong together**.

The **Canopy** tells us what shape those structures form when viewed as a liquidity graph.



Examples include:

* ⭐ **Hub-and-Spoke**
* 🌻 **Sunflower**
* 🔄 **Ring**
* 🕸️ **Mesh**
* 🌳 **Hierarchical**
* 🧬 **Hybrid**



These are **not Grove classes**.

They are the resulting liquid topology emerging from these grove classes.



For example:

* a **Reserve Grove** can exhibit Hub-and-Spoke topology;
* an **Arbitrage Guild** can form a Ring;
* several **Weighted Grafts** can form a Sunflower;
* several overlapping Groves can contribute to the same Mesh.



{% hint style="info" %}
## 🌿 Grove vs. Canopy

**Grove:** why these structures belong together.

**Canopy:** what shape their connections create.
{% endhint %}



***

## 🌻 The Sunflower Example

The first deliberate Graft deployment makes the distinction concrete.

Several three-token weighted pools share **wNUT** as common rootstock.



Each individual pool is a:

> 🌱 **Graft**



Together they form a:

> 🌻 **Sunflower Canopy Form**



The initial Grafts use the same weight geometry:

```
20% wNUT
40% Scion A
40% Scion B
```



Examples include Scion pairs representing:

* Bitcoin;
* Ethereum;
* stable settlement;
* AI;
* agents;
* inference.



The shared rootstock produces a rooted hyperstar:

```
                  VVV / DIEM
                      │
                      │
               VIRTUAL / MOR
                      │
                      │
cbETH / wstETH ──── wNUT ──── cbBTC / tBTC
                      │
                      │
                  USDC / EURC
```



Each apparent “petal” represents an entire three-token Graft rather than a simple edge.



The Sunflower therefore demonstrates three separate dimensions at once:

1. **Structure** — each pool is a Graft.
2. **Weight** — each begins at `20 / 40 / 40`.
3. **Topology** — together they form a shared-root hyperstar.



***

## 🧬 Polyculture

The Orchard is not built from one AMM mechanism repeated everywhere.



It contains different forms of liquidity simultaneously:

* Branches;
* Grafts;
* Whorls;
* bonding curves;
* constant-product markets;
* concentrated liquidity;
* weighted pools;
* reCLAMM;
* wrappers;
* nested liquidity claims.

These mechanisms can connect into common routes.



One existing pattern can be represented as:

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

This closes a liquidity Ring while traversing several pricing mechanisms.



Another route can connect:

```
NUT
 ↓
NUTINO
 ↓
cbBTC
 ↓
NUT
```



A single route can therefore cross several **Cultivation Groves** while simultaneously participating in a **Routing Guild**, **Arbitrage Guild**, or **Price-Discovery Guild**.



That is liquidity **polyculture**.



***

## 🌳 The Three Current Practical Groves

The deployed Orchard can now be viewed through three major regions.

| Grove             | Character     | Dominant structural idea                        |
| ----------------- | ------------- | ----------------------------------------------- |
| 🌻 **Sunflower**  | standardized  | rooted Grafts                                   |
| 🏺 **Heirloom**   | inherited     | foundational Branches, Whorls, nested liquidity |
| 🌲 **Polyforest** | heterogeneous | mixed structures and mechanisms interacting     |

Their differences are easiest to see side by side.



#### 🌻 Sunflower

```
same rootstock
same initial geometry
different Scions
```



#### 🏺 Heirloom

```
historical NUT lineage
early markets
structures accumulated over time
```



#### 🌲 Polyforest

```
different assets
different protocols
different mechanisms
shared routes
```

Together, they describe how the modern Orchard actually grew.



***



## 🔄 A Living Orchard

The Orchard is not only a graph.



It is a graph whose economic state changes continuously.



Let the Orchard's state at time `t` be:

$$
\Sigma_t
$$

An economic action transforms that state:

$$
\Sigma_t \longrightarrow \Sigma_{t+1}
$$

State may include:

* token balances;
* spot prices;
* implied relative prices;
* pool weights;
* liquidity depth;
* LP supply;
* active concentrated-liquidity ranges;
* ticks;
* fees;
* mint state;
* burn state;
* wrapper state;
* bonding-curve state;
* routing state;
* arbitrage conditions.



#### 🐝 Dynamic Guilds

Some Grove relationships are persistent.

Examples:

* Reserve;
* Compute;
* NUT Lineage.

Others depend directly on state.



Examples:

* Arbitrage;
* Routing;
* Price Discovery;
* Rebalancing.



A market can therefore belong to a Guild at one state and not at the next.

$$
G_i \in \mathcal{G}_t
$$

followed by:

$$
G_i \notin \mathcal{G}_{t+1}
$$



A Grove can therefore represent a **live economic projection**, not merely a static category.

$$
\Sigma_t
\xrightarrow{\text{economic action}}
\Sigma_{t+1}
$$

***

## 🌳 The Complete Orchard

A compact mathematical representation of the system is:

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
* **E** — liquidity structures and venues;
* **I(e)** — assets participating in structure `e`;
* **λ(e)** — structure metadata;
* **r = wNUT** — distinguished Graft rootstock;
* **Σₜ** — mutable economic state.



The metadata attached to a liquidity structure can include:

* Branch / Graft / Whorl;
* venue;
* pricing mechanism;
* weights;
* fee tier;
* deployment;
* lineage;
* active state;
* historical classification.



The Orchard can therefore be described as:

> **a rooted, typed, multiplex liquidity hypergraph with mutable economic state.**



***

## 🌳 The Layers of the Orchard

The system is a composition of layers, not a linear chain mediated by NUT and wNUT.



```
                         ASSETS
                           │
          ┌────────────────┼────────────────┐
          │                │                │
         NUT             wNUT          other assets
          │                │                │
          └────────────────┼────────────────┘
                           │
                           ▼
              LIQUIDITY STRUCTURES
                           │
             ┌─────────────┼─────────────┐
             │             │             │
          Branch         Graft         Whorl
             │             │             │
             └─────────────┼─────────────┘
                           │
                           ▼
                   GROVE PROJECTIONS
                           │
       ┌───────────────────┼───────────────────┐
       │                   │                   │
      Crop               Guild            Cultivation
                                               │
                         Heritage ──────────────┘
                           │
                           ▼
                    CANOPY TOPOLOGY
                           │
                           ▼
                       ORCHARD
                           │
                           ▼
                    MUTABLE STATE
```

wNUT is specifically the common **rootstock of Grafts**.

It is not a mandatory intermediary for every Branch, Whorl, curve, or other market in the Orchard.

But this adds specificity to the wNUT role.

***

## .🗺️ Reading Any Part of the Orchard

For any liquidity structure, ask these questions in order.



#### 1. 🔬 What is it?

* 2-token → **Branch**
* rooted `{wNUT + Scion + Scion}` → **Graft**
* other 3+ token → **Whorl**



#### 2. ⚖️ How is it weighted?

Examples:

* `50 / 50`
* `20 / 40 / 40`
* `25 / 25 / 25 / 25`
* concentrated range
* another market geometry



#### 3. 🌾 What grows there?

**Crop Grove**

* Reserve
* Settlement
* Compute
* Infrastructure
* Capital



#### 4. 🐝 What does it do?

**Guild Grove**

* Routing
* Arbitrage
* Price Discovery
* Cross-Pollination
* Yield
* Rebalancing
* Attestation



#### 5. 🌱 How is it cultivated?

**Cultivation Grove**

* Bonding Curve
* Constant Product
* Concentrated Liquidity
* Weighted
* reCLAMM



#### 6. 🧬 Where did it come from?

**Heritage Grove**

* NUT Lineage
* Nested Lineage
* Heirloom
* provenance



#### 7. 🌿 What shape does it help create?

**Canopy Form**

* Hub-and-Spoke
* Sunflower
* Ring
* Mesh
* Hierarchical
* Hybrid



#### 8. 🔄 What state is it in?

Current:

* balances;
* prices;
* weights;
* liquidity;
* routes;
* arbitrage;
* LP state.



***

## 🥜 Canonical Orchard Vocabulary

<table><thead><tr><th width="201">Term</th><th>Meaning</th></tr></thead><tbody><tr><td>🥜 <strong>NUT</strong></td><td>underlying root asset</td></tr><tr><td>🌱 <strong>wNUT</strong></td><td>common Graft rootstock</td></tr><tr><td>🌿 <strong>Scion</strong></td><td>asset attached through a Graft</td></tr><tr><td>🌿 <strong>Branch</strong></td><td>2-token liquidity pool</td></tr><tr><td>🌱 <strong>Graft</strong></td><td>rooted <code>{wNUT + Scion + Scion}</code> three-token pool</td></tr><tr><td>🌸 <strong>Whorl</strong></td><td>any other 3+ token pool</td></tr><tr><td>🌳 <strong>Grove</strong></td><td>semantic subgraph projection</td></tr><tr><td>🌾 <strong>Crop</strong></td><td>economic exposure</td></tr><tr><td>🐝 <strong>Guild</strong></td><td>economic function</td></tr><tr><td>🌱 <strong>Cultivation</strong></td><td>pricing / liquidity mechanism</td></tr><tr><td>🧬 <strong>Heritage</strong></td><td>lineage / provenance</td></tr><tr><td>🌿 <strong>Canopy</strong></td><td>graph topology</td></tr><tr><td>🔄 <strong>State</strong></td><td>current mutable economic condition</td></tr><tr><td>🌱 <strong>Nursery</strong></td><td>proposed or undeployed structures</td></tr><tr><td>🌳 <strong>Orchard</strong></td><td>complete liquidity system</td></tr></tbody></table>



{% hint style="info" %}
### 🥜 One word, one concept

**The pool tells you its structure.**

**The weights tell you its balance.**

**The Grove tells you its relationship.**

**The Canopy tells you its shape.**

**The state machine tells you how it changes.**

**The Orchard contains all of it.**
{% endhint %}

