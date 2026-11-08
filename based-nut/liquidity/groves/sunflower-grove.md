# 🌻 Sunflower Grove

**The first deployed Graft system in the Orchard.**

The **Sunflower Grove** is the first concrete implementation of the Graft framework: five three-token weighted pools sharing **wNUT** as a common rootstock.



Each pool contains:

* **20% wNUT**
* **40% Scion A**
* **40% Scion B**



This configuration is called a **Twin Graft**.



Individually, each pool is a **Graft**.



Together, the five Grafts form the **Sunflower Grove**.

Viewed as a graph, their shared-root geometry creates the **Sunflower Canopy Form**.



{% hint style="success" %}
## 🌻 Sunflower at a glance

**5 Grafts**

**15 pool positions across 11 unique assets**

**1 common rootstock: wNUT**

**1 shared geometry: 20 / 40 / 40**

**5 different Scion pairings**

The weights stay constant while the assets change.
{% endhint %}



***

## 🌱 The Twin Graft

Every pool in the initial Sunflower has exactly three assets.

$${\mathrm{wNUT},s_i,s_j}$$

where:

* **wNUT** is the shared rootstock;
* **sᵢ** is the first Scion;
* **sⱼ** is the second Scion.



The initial weight geometry is:

$$
20%\ \mathrm{wNUT}
+
40%\ s_i
+
40%\ s_j
$$

Visually:

```
          40% Scion A
               \
                \
              20% wNUT
                /
               /
          40% Scion B
```

This specific implementation is a:

> 🌱 **Twin Graft**

The word **Twin** refers to the two equally weighted Scions.

The word **Graft** refers to the rooted three-token structure.



***

## 🌻 The Five Initial Grafts

The Sunflower begins with five Twin Grafts.

| Graft                  | Rootstock |     Scion A |    Scion B | Primary economic relationship |
| ---------------------- | --------: | ----------: | ---------: | ----------------------------- |
| ◆ **Ethereum Graft**   |  20% wNUT |   40% cbETH | 40% wstETH | Ethereum reserve assets       |
| ₿ **Bitcoin Graft**    |  20% wNUT |   40% cbBTC |   40% tBTC | Bitcoin reserve assets        |
| 💵 **Forex Graft**     |  20% wNUT |    40% USDC |   40% EURC | fiat-denominated settlement   |
| 🤖 **Agent Graft**     |  20% wNUT | 40% VIRTUAL |    40% MOR | AI and autonomous agents      |
| 🧠 **Inference Graft** |  20% wNUT |     40% VVV |   40% DIEM | AI and inference              |

Each pool has different Scions.

Every pool shares the same rootstock and initial weight geometry.

***

## 🌿 One Rootstock

The defining feature of the Sunflower is not simply that five weighted pools exist.

It is that **every Graft contains wNUT**.

For five Grafts:

$$
G_1,G_2,G_3,G_4,G_5
$$

their common-root condition is:

$$
\mathrm{wNUT}
\in
\bigcap_{k=1}^{5}G_k
$$

The rootstock is therefore the structural point shared by the entire system.

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

Each apparent petal represents one complete three-token Graft:

```
{wNUT, cbETH, wstETH}

{wNUT, cbBTC, tBTC}

{wNUT, USDC, EURC}

{wNUT, VIRTUAL, MOR}

{wNUT, VVV, DIEM}
```

The diagram is therefore a **hypergraph**, not merely a set of pairwise edges.

***

## 🥜 Why wNUT?

NUT is the root asset of the wider Orchard.

wNUT provides a standardized form of NUT that can serve as common liquidity rootstock across the Graft system.



The relationship is:

$$
1\ \mathrm{NUT}
\longleftrightarrow
1\ \mathrm{wNUT}
$$

This allows the Grafts to share a common structural asset without redefining NUT itself around the needs of the experimental pool system.



The distinction remains:

* 🥜 **NUT** — root asset of the Orchard;
* 🌱 **wNUT** — rootstock of the Graft system.



wNUT does not need to dominate a pool by weight to act as its rootstock.



Its role is structural.

***

## ⚖️ Why 20 / 40 / 40?

The first Sunflower deliberately uses the same weights in every Graft.

$$
20 / 40 / 40
$$

This creates a controlled baseline.

If both the **assets** and the **weights** changed from pool to pool, differences in behavior would be difficult to interpret.

Instead, the initial system holds one variable constant:

> **weight geometry**

while changing:

> **Scion composition**

This makes each Graft comparable to the others.



***

### 🌱 Two equal Scions

The two Scions each receive **40%**.

This gives them equal structural importance inside the pool.

For a Twin Graft:

$$
w_{s_i}=w_{s_j}=0.40
$$

The system is therefore not designed around a dominant primary Scion and subordinate secondary Scion.

The two assets form a pair.

***

### 🥜 Smaller common rootstock

wNUT receives **20%**.

$$
w_{\mathrm{wNUT}}=0.20
$$

This is large enough for wNUT to participate directly in each weighted market while leaving most of the pool's weight with the two Scions being compared.



The geometry can be read as:



```
            Scion pair
         ┌──────┴──────┐
        40%           40%
          \     g     /
           \         /
             20% wNUT
```

The rootstock connects the Grafts(g).

The Scions define the economic character of each individual Graft.

***

## 🔬 What Changes Between Grafts?

Only the Scion pair.

#### ◆ Ethereum

```
20% wNUT
40% cbETH
40% wstETH
```

#### ₿ Bitcoin

```
20% wNUT
40% cbBTC
40% tBTC
```

#### 💵 Settlement

```
20% wNUT
40% USDC
40% EURC
```

#### 🤖 Agents

```
20% wNUT
40% VIRTUAL
40% MOR
```

#### 🧠 Inference

```
20% wNUT
40% VVV
40% DIEM
```

This allows five different economic relationships to be observed through the same liquidity structure.



***

## 🌾 The Crop Lens

The five Grafts are not five isolated experiments.

They deliberately span several parts of the economic Orchard.



#### ₿ Reserve

* cbBTC / tBTC
* cbETH / wstETH

#### 💵 Settlement

* USDC / EURC

#### 🤖 Compute

* VIRTUAL / MOR
* VVV / DIEM



The Sunflower therefore brings several **Crop Groves** into one shared structural system.

This is the first practical demonstration that a Graft can have one structural identity while participating in a wider economic classification.



***

## 🐝 Cross-Pollination



The Scions do not need to belong to the same broader Grove forever.

Future Grafts can deliberately connect different economic domains.



For example:

```
        AI Scion
           \
            \
           wNUT
            /
           /
      Bitcoin Scion
```



Such a Graft could simultaneously belong to:

* 🤖 Compute Grove;
* ₿ Reserve Grove;
* 🐝 Cross-Pollination Guild;
* ⚖️ Weighted Cultivation Grove.



This is where the Graft framework becomes more than a collection of themed pools.

A single rooted market can connect different regions of the Orchard.

***

## 🔭 What Is Being Observed?

The Sunflower is an experimental liquidity system.

Its initial objective is not simply to maximize TVL.

The five common-weight Grafts provide a controlled environment for observing how rooted multi-asset markets behave individually and together.

***

### 💹 1. Relative market behavior

How do the two Scions behave relative to:

* each other;
* wNUT;
* their external markets?

A Twin Graft contains three simultaneous economic relationships.

For:

$$
G={\mathrm{wNUT},A,B}
$$

the pool contains information about:

```
A ↔ B

A ↔ wNUT

B ↔ wNUT
```

One three-token pool therefore exposes more relational structure than one ordinary pair.

***

### ⚖️ 2. Weighted rebalancing

External prices move.

The weighted pool reacts.

That creates pressure for trading and rebalancing inside the Graft.



The experiment can observe how the common:

$$
20 / 40 / 40
$$

geometry behaves across very different asset classes.



Questions include:

* How quickly does each Graft move away from its initial state?
* Which Scion relationships create the strongest rebalancing pressure?
* How does wNUT inventory change?
* How often does external arbitrage restore relative alignment?

***

### ♻️ 3. Arbitrage

Each Scion may already trade elsewhere.

wNUT and NUT also participate in the wider Orchard.

The Grafts therefore create new relative-price relationships against external venues.



Possible arbitrage paths can emerge between:

* Scion ↔ Scion;
* Scion ↔ NUT;
* Scion ↔ wNUT;
* one Graft ↔ another Graft;
* Graft ↔ external AMM;
* Graft ↔ wider Orchard route.



The Sunflower can reveal where those relationships become economically actionable.

***

### 🛣️ 4. Routing

A Graft is not only a destination for liquidity.

It can become part of a route.



A trade path may enter through one Scion and leave through:

* the second Scion;
* wNUT;
* NUT through wrapping or unwrapping;
* another part of the Orchard.

As more structures connect, the Sunflower can become routing infrastructure rather than five isolated weighted pools.



***

### 🌼 5. Price discovery

Each Graft creates another venue through which relative prices can be expressed.



The system can observe:

* whether Graft prices lead or follow external markets;
* how thin experimental liquidity responds to external movement;
* how quickly price discrepancies propagate;
* whether one Graft creates useful information for another.



***

### 🐝 6. Cross-Graft interaction

Every Graft shares wNUT.

A state change in one pool can therefore alter economic conditions around the common rootstock.



That does not mean every trade mechanically changes every other Graft.

It means they participate in a larger shared market environment.

```
Graft A
   \
    \
    wNUT
    / \
   /   \
Graft B Graft C
```

Changes in:

* wNUT demand;
* NUT/wNUT flows;
* relative pricing;
* arbitrage incentives;
* routing;



can create relationships between otherwise separate Grafts.



***

## 🔄 The Sunflower as a State Machine

The deployed contracts define the structure.

Trading makes the structure dynamic.



Let the state of the complete Sunflower at time `t` be:

$$
\Sigma_{\mathrm{Sunflower},t}
$$



An action inside one Graft changes part of that state:

$$
\Sigma_{\mathrm{Sunflower},t}
\longrightarrow
\Sigma_{\mathrm{Sunflower},t+1}
$$

Relevant state includes:

* Graft balances;
* relative prices;
* wNUT inventory;
* LP ownership;
* fees;
* external price relationships;
* arbitrage opportunities;
* active routing relationships.



The Sunflower is therefore not only a topology.

It is a **live economic system moving through states**.

***

## 🌻 The Sunflower Canopy

The five Grafts form one recognizable shape because they all share wNUT.



This is the **Sunflower Canopy Form**.



Mathematically, the Grafts form a common-root hyperstar.



Visually:

```
                  🌼
              VVV / DIEM
                   │
                   │
      🌼           │           🌼
cbETH / wstETH ── wNUT ── cbBTC / tBTC
                 │     │
                 │     │
       USDC / EURC     VIRTUAL / MOR
               🌼     🌼

                  
```

The individual petals are Grafts.

The shared center is wNUT.



The complete shape is the Sunflower.



***

## 🌳 One System, Several Lenses

The Sunflower is the first place where the Orchard ontology becomes concrete.



Take the Bitcoin Twin Graft:

```
20% wNUT
40% cbBTC
40% tBTC
```

It can be read several ways.



#### 🌱 Structure

**Graft**

It is a rooted three-token pool.



#### ⚖️ Weight

**20 / 40 / 40**

It is a Twin Graft.



#### 🌾 Crop

**Reserve Grove**

Its Scions are Bitcoin reserve assets.



#### 🐝 Guild

Depending on current use and state, it may participate in:

* Routing;
* Arbitrage;
* Price Discovery;
* Rebalancing;
* Attestation.



#### 🌱 Cultivation

**Weighted Grove**

Its market behavior comes from weighted liquidity.



#### 🧬 Heritage

Its assets and contracts retain their own provenance and lineage.



#### 🌻 Canopy

**Sunflower**

It is one petal in the common-root hyperstar.



One pool can therefore be described across the entire framework without changing what the pool actually is.



***

## 🧪 Why Start Small?

The Sunflower is deliberately experimental.

The first objective is to create **observable topology**, not to force maximum liquidity into every Graft.



Smaller positions allow the system to establish:

* actual market relationships;
* real state transitions;
* real routing possibilities;
* real arbitrage conditions;
* comparable pool behavior;

without requiring every experimental market to become a major liquidity venue immediately.





#### 🌱 The first planting

The purpose of the initial Sunflower is to make the Graft system **real enough to observe**.

Once deployed, the framework is no longer only an ontology.

It has economic state.<br>

## 🔬 What the Experiment Can Compare

Because all five pools begin from the same architecture, they can be compared across several dimensions.

| Observation          | Held constant     | Variable                  |
| -------------------- | ----------------- | ------------------------- |
| Scion behavior       | 20/40/40 geometry | assets                    |
| Rebalancing          | rooted Graft form | external price movement   |
| Arbitrage            | common rootstock  | external venue structure  |
| Routing              | wNUT connection   | surrounding Orchard paths |
| Volatility response  | pool architecture | asset class               |
| Cross-Graft activity | shared wNUT       | Scion economics           |

This is the principal value of the common starting geometry.

The Sunflower changes one major variable at a time.



***

## 🌱 Future Grafts

The first Sunflower does not define the only permissible Graft weights.



A Graft remains:

$${\mathrm{wNUT},s_i,s_j}$$

regardless of whether its weights are:

```
20 / 40 / 40
33 / 33 / 33
50 / 25 / 25
70 / 20 / 10
```

Future Grafts can test different weight geometries for different economic purposes.

They can also connect:

* assets from the same Crop Grove;
* assets from different Crop Groves;
* protocol assets;
* reserve assets;
* settlement assets;
* productive capital;
* new experimental Scions.

The **Graft definition stays fixed** while its economic design space expands.

***

## 🌳 From Five Pools to a Liquidity Graph

At first glance, the implementation is simple:

```
5 weighted pools
```

But the shared rootstock changes what those pools become collectively.



The system contains:

* five independent markets;
* ten distinct Scion positions;
* one common rootstock;
* several economic domains;
* new relative-price relationships;
* new routing possibilities;
* new arbitrage relationships;
* observable market-state transitions.



That converts a pool collection into a **liquidity topology**.

***

## 🥜 The Sunflower Rule

#### 🌻 One implementation, the whole framework



**Each pool is a Graft.**

**Each initial Graft is a 20/40/40 Twin Graft.**



**wNUT is the common rootstock.**

**The Scions determine each Graft's economic character.**

**Groves describe the relationships those Grafts participate in.**

**Together, the five Grafts create the Sunflower Canopy.**

**Their changing balances and prices create live Orchard state.**<br>

The Sunflower is the first planting where the Orchard can be observed not just as a metaphor or graph model, but as an operating liquidity system.
