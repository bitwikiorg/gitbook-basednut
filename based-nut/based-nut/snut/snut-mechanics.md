# 🔥 SNUT Mechanics

SNUT is the mechanical layer of the BASED NUT ecosystem.



The surface behavior is simple:

> **Hold SNUT → earn NUT.**&#x20;
>
> **Trade SNUT → feed the system.**

Underneath that is a chain of linked market actions.



***

### 🔄 Fee Routing

Every SNUT transfer currently applies a **1% fee**.

That fee is routed across four functions.

{% code expandable="true" %}
```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'#ffffff',
  'primaryColor':'#fdf6e3',
  'primaryTextColor':'#111111',
  'primaryBorderColor':'#7c5a10',
  'lineColor':'#6b7280',
  'secondaryColor':'#eef2ff',
  'tertiaryColor':'#f9fafb',
  'fontSize':'15px'
}}}%%
flowchart TD
    A["🦸 SNUT Transfer / Trade"]
    B["💧 1% Fee"]
    C["🌊 Liquidity"]
    D["🛠️ Manager"]
    E["🔥 Buyback / Burn"]
    F["🌰 NUT Rewards"]

    A --> B
    B --> C
    B --> D
    B --> E
    B --> F

    classDef action fill:#f6c453,stroke:#6b4b16,stroke-width:3px,color:#111;
    classDef core fill:#fff3d6,stroke:#a97922,stroke-width:3px,color:#111;
    classDef liquidity fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#111;
    classDef manager fill:#ede9fe,stroke:#7c3aed,stroke-width:2px,color:#111;
    classDef burn fill:#fee2e2,stroke:#dc2626,stroke-width:2px,color:#111;
    classDef reward fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#111;

    class A action;
    class B core;
    class C liquidity;
    class D manager;
    class E burn;
    class F reward;
```
{% endcode %}

The exact live split should always be verified from the contract.



***

### ⚙️ Swapback Engine

Collected fee-bearing SNUT does not stop at collection.

It is processed through a swapback path that turns the fee flow into usable outputs.

{% code expandable="true" %}
```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'#ffffff',
  'primaryTextColor':'#111111',
  'lineColor':'#6b7280',
  'fontSize':'15px'
}}}%%
flowchart LR
    A["🦸 SNUT Activity"]
    B["📦 Fee Accumulation"]
    C["⚙️ Swapback"]
    D["Ξ ETH / Routed Assets"]

    E["🌊 Liquidity"]
    F["🛠️ Manager"]
    G["🔥 Buyback / Burn"]
    H["🌰 NUT Rewards"]

    A --> B --> C --> D
    D --> E
    D --> F
    D --> G
    D --> H

    classDef source fill:#f6c453,stroke:#6b4b16,stroke-width:3px,color:#111;
    classDef process fill:#fff3d6,stroke:#a97922,stroke-width:3px,color:#111;
    classDef output fill:#eef2f7,stroke:#6b7280,stroke-width:2px,color:#111;
    classDef liquidity fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#111;
    classDef manager fill:#ede9fe,stroke:#7c3aed,stroke-width:2px,color:#111;
    classDef burn fill:#fee2e2,stroke:#dc2626,stroke-width:2px,color:#111;
    classDef reward fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#111;

    class A source;
    class B,C process;
    class D output;
    class E liquidity;
    class F manager;
    class G burn;
    class H reward;
```
{% endcode %}

This is why SNUT transfers can create downstream market effects rather than just moving balances.



***

### 🌰 Non-Escrow Reward Position

SNUT holders do not need to lock tokens in a traditional escrow staking contract.

{% code expandable="true" %}
```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'#ffffff',
  'primaryTextColor':'#111111',
  'lineColor':'#6b7280',
  'fontSize':'15px'
}}}%%
flowchart LR
    A["🦸 Hold SNUT"]
    B["🔓 Stay Liquid"]
    C["🌰 Earn NUT"]

    A --> B
    A --> C

    classDef hold fill:#f6c453,stroke:#6b4b16,stroke-width:3px,color:#111;
    classDef benefit fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#111;
    classDef state fill:#eef2f7,stroke:#6b7280,stroke-width:2px,color:#111;

    class A hold;
    class B state;
    class C benefit;
```
{% endcode %}

> **SNUT is a liquid reward position for NUT.**

***

### 🔥 Recursive Compounding Burn Flywheel

One of the most unusual SNUT mechanics is the recursive burn path.

Buybacks can send SNUT to the dead address.

If dead-held SNUT remains inside reward accounting, it can continue receiving NUT rewards. Those NUT can also accumulate at dead.

{% code expandable="true" %}
```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'#ffffff',
  'primaryTextColor':'#111111',
  'lineColor':'#6b7280',
  'fontSize':'15px'
}}}%%
flowchart TD
    A["🦸运� SNUT Activity"]
    B["💧 Fee Flow"]
    C["🔥 Buyback"]
    D["☠️ Dead-Held SNUT"]
    E["🌰 NUT Rewards"]
    F["☠️ Dead-Held NUT"]

    A --> B --> C --> D
    D --> E --> F

    classDef source fill:#f6c453,stroke:#6b4b16,stroke-width:3px,color:#111;
    classDef fee fill:#fff3d6,stroke:#a97922,stroke-width:3px,color:#111;
    classDef burn fill:#fee2e2,stroke:#dc2626,stroke-width:2px,color:#111;
    classDef reward fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#111;
    classDef dead fill:#f3f4f6,stroke:#4b5563,stroke-width:2px,color:#111;

    class A source;
    class B fee;
    class C burn;
    class D,F dead;
    class E reward;
```
{% endcode %}

> **Burn feeds burn.**

Important distinction: sending tokens to dead removes them from effective circulation, but it does not rewrite the token’s original total-supply constant.



***

### 🌊 SNUT Liquidity Layers

SNUT lives across multiple market layers.

Each pool has a different job.

{% code expandable="true" %}
```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'#ffffff',
  'primaryTextColor':'#111111',
  'lineColor':'#6b7280',
  'fontSize':'15px'
}}}%%
flowchart TD
    SNUT["🦸 SNUT"]

    UNI["🎠 SNUT / WETH<br/>Main Market"]
    LP["🧾 SNUT/WETH LP"]
    META["🌴 SNUT-LP / WETH<br/>Meta-Market"]
    NUT["🌰 SNUT / NUT<br/>Reactor"]
    BASKET["⚖️ Multi-Asset Exposure"]

    SNUT --> UNI
    UNI --> LP
    LP --> META
    SNUT --> NUT
    SNUT --> BASKET

    classDef snut fill:#f6c453,stroke:#6b4b16,stroke-width:4px,color:#111;
    classDef market fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#111;
    classDef lp fill:#fff3d6,stroke:#a97922,stroke-width:2px,color:#111;
    classDef meta fill:#ede9fe,stroke:#7c3aed,stroke-width:2px,color:#111;
    classDef reactor fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#111;
    classDef basket fill:#fce7f3,stroke:#db2777,stroke-width:2px,color:#111;

    class SNUT snut;
    class UNI market;
    class LP lp;
    class META meta;
    class NUT reactor;
    class BASKET basket;
```
{% endcode %}

#### Pool Roles

| Pool                     | Role                                         |
| ------------------------ | -------------------------------------------- |
| **SNUT / WETH**          | Primary spot liquidity and price discovery   |
| **SNUT-LP / WETH**       | Secondary market for the LP token itself     |
| **SNUT / NUT**           | Direct reactor connection into the NUT graph |
| **Multi-asset exposure** | Additional shared liquidity relationships    |

***

### 🌴 The Palm Tree Market

The `SNUT-LP / WETH` pool is a meta-market.

It gives the **SNUT/WETH LP token** its own market price.

{% code expandable="true" %}
```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'#ffffff',
  'primaryTextColor':'#111111',
  'lineColor':'#6b7280',
  'fontSize':'15px'
}}}%%
flowchart LR
    A["🦸 SNUT"]
    B["Ξ WETH"]
    C["🧾 SNUT/WETH LP"]
    D["🌴 LP / WETH Market"]

    A --> C
    B --> C
    C --> D

    classDef token fill:#f6c453,stroke:#6b4b16,stroke-width:3px,color:#111;
    classDef base fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#111;
    classDef lp fill:#fff3d6,stroke:#a97922,stroke-width:2px,color:#111;
    classDef meta fill:#ede9fe,stroke:#7c3aed,stroke-width:2px,color:#111;

    class A token;
    class B base;
    class C lp;
    class D meta;
```
{% endcode %}

This creates another pricing layer:

```
SNUT spot
+ WETH spot
+ SNUT/WETH LP value
+ SNUT-LP/WETH market price
```

That separation can produce additional arbitrage and repricing behavior.

> **Liquidity itself becomes liquid.**



***

### 🧮 Cascading State

SNUT is one of the clearest examples of layered economic state inside BASED NUT.

A single transfer can propagate through multiple compartments.

{% code expandable="true" %}
```mermaid
%%{init: {'theme':'base','themeVariables':{
  'background':'#ffffff',
  'primaryTextColor':'#111111',
  'lineColor':'#6b7280',
  'fontSize':'15px'
}}}%%
flowchart TD
    A["S₀<br/>🦸 SNUT Transfer"]
    B["S₁<br/>💧 Fee State"]
    C["S₂<br/>⚙️ Swapback State"]
    D["S₃<br/>🌊 Liquidity State"]
    E["S₄<br/>🌰 Reward State"]
    F["S₅<br/>🔥 Buyback State"]
    G["S₆<br/>📈 New Market State"]

    A --> B --> C
    C --> D
    C --> E
    C --> F
    D --> G
    E --> G
    F --> G

    classDef s0 fill:#f6c453,stroke:#6b4b16,stroke-width:3px,color:#111;
    classDef s1 fill:#fff3d6,stroke:#a97922,stroke-width:2px,color:#111;
    classDef s2 fill:#eef2f7,stroke:#6b7280,stroke-width:2px,color:#111;
    classDef s3 fill:#dbeafe,stroke:#2563eb,stroke-width:2px,color:#111;
    classDef s4 fill:#dcfce7,stroke:#16a34a,stroke-width:2px,color:#111;
    classDef s5 fill:#fee2e2,stroke:#dc2626,stroke-width:2px,color:#111;
    classDef s6 fill:#fce7f3,stroke:#db2777,stroke-width:3px,color:#111;

    class A s0;
    class B s1;
    class C s2;
    class D s3;
    class E s4;
    class F s5;
    class G s6;
```
{% endcode %}

> **One token action can propagate through rewards, liquidity, burns, and multiple market states.**



***

### Contracts & Markets

<table><thead><tr><th width="261">Component</th><th>Address</th></tr></thead><tbody><tr><td><strong>SNUT</strong></td><td><code>0xAC130701aa31c284c36609E2489f150F419AD7AD</code></td></tr><tr><td><strong>SNUT/WETH LP</strong></td><td><code>0xb22895d2ee6e29395f30ec47c8d9fe0d55355ae1</code></td></tr><tr><td><strong>SNUT-LP/WETH Meta-Pool</strong></td><td><code>0x82bbadb9d6b2c0a59ed01809e30323f89f6faa1c</code></td></tr><tr><td><strong>SNUT/NUT</strong></td><td><code>0x893faaa7baf7a8247fc7142afb28e13d51a5aae8</code></td></tr></tbody></table>

> ⚠️ **Experimental Memefi.** Contract behavior, fee configuration, liquidity, and market state should always be independently verified before interaction.
