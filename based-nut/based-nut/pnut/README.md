---
description: The NUT Index Token
cover: ../../.gitbook/assets/Noot (1).png
coverY: 0
layout:
  width: default
  cover:
    visible: true
    size: hero
    mask: none
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
  anchors:
    visible: true
---

# 🥜 pNUT

## BASED PEANUT ($pNUT)

### Overview

**BASED PEANUT ($pNUT)** is an index token within the BASED NUT ecosystem. This index structure offers holders a simplified and efficient way to participate in the broader DeFi landscape, benefiting from a wide range of assets within the BASED NUT ecosystem.

It provides exposure to a basket of diversified assets combining them into a single token.

<figure><img src="../../.gitbook/assets/DALL·E 2024-09-05 21.01.49 - A 3D character resembling a peanut, with a cute and adorable kawaii design. The character has a smooth, light brown peanut-shaped body, large expressi.webp" alt="" width="188"><figcaption><p>Peanutoshi Nutkamoto</p></figcaption></figure>

**BASED PEANUT ($pNUT)** is the index and liquidity token for a Balancer V2 weighted pool containing:

* 🌰 **NUT**
* 🦸 **SNUT**
* Ξ **cbETH**
* ₿ **cbBTC**

Each asset has a **25% pool weight**, combining BASED NUT assets with ETH and Bitcoin exposure in a single pool.

pNUT itself is the **Balancer Pool Token (BPT)**.

Holding pNUT represents proportional ownership of the assets held by the pool.

> **Four assets. One pool. One token representing the basket.**



Unlike many DeFi protocols that rely on emissions or minting new tokens, $pNUT generates real yield through market activity.

### Key Features

#### ⚖️ **Index-Based Structure**

$pNUT aggregates four assets with equal pool weights:

| Asset   | Weight |
| ------- | -----: |
| 🌰 NUT  |    25% |
| 🦸 SNUT |    25% |
| Ξ cbETH |    25% |
| ₿ cbBTC |    25% |

Instead of holding four separate positions, pNUT represents a share of the entire pool.

***

#### 💧 Trading Fees

The basket is also a live market.

Trades between its underlying assets pay Balancer swap fees, which accrue to the pool and its liquidity providers.

More market activity can therefore generate more fee income for the pool.

***

#### Ξ Staking-Yield Exposure

One quarter of the basket is **cbETH**, Coinbase's liquid representation of staked ETH.

cbETH includes the economic value and rewards of the underlying staked ETH, giving pNUT exposure to Ethereum staking rewards in addition to pool trading activity.

***

#### 🌊 Volatility Farming

Price fluctuations between $pNUT and its underlying assets create arbitrage opportunities. Traders can capitalize on these price differences, generating fees that are distributed to participants in the ecosystem.

The four assets move independently. When their relative market prices change, arbitrageurs can trade against the Balancer pool to bring its prices back toward external markets.

```
price movement
      ↓
price difference
      ↓
arbitrage
      ↓
pool trades
      ↓
trading fees
```

Volatility creates rebalancing activity, and rebalancing activity can create fees.



***

#### 🐝 Arbitrage

pNUT connects several otherwise separate markets.

For example, NUT may trade elsewhere on Uniswap or Aerodrome while the Balancer pool simultaneously contains NUT alongside cbBTC, cbETH, and SNUT.

Differences between those markets can create arbitrage paths.

> **The basket does not need to predict the correct price. Markets continuously compare it with the rest of the liquidity graph.**



***

### Technical Details

<figure><img src="../../.gitbook/assets/DALL·E 2024-09-18 18.48.24 - A hyper-realistic 3D peanut logo designed for a peanut-based brand. The peanut is rendered with intricate details, lifelike textures, and natural colo.webp" alt="" width="188"><figcaption><p>BASED PEANUT</p></figcaption></figure>

{% tabs %}
{% tab title="Technical Details" %}
## **pNUT V1 Technical Details**

| Technical Details |                                            |
| ----------------- | ------------------------------------------ |
| Token Name        | BASED PEANUT ($pNUT)                       |
| Chain             | BASE                                       |
| Index Components  | cbETH, cbBTC, NUT, SNUT                    |
| Token Address     | 0x2A5757b60987FF10385De1D4D923792f6fdCfFf1 |
| Symbol            | $pNUT                                      |
| Total Supply      | ∞                                          |
{% endtab %}

{% tab title="Liquidity" %}
## Liquidity

### ⚖️ **Balancer**

* [**pNUT - (25cbETH-25SNUT-25NUT-25cbBTC)**](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000000019e)
  * &#x20;:peanuts: **pNUT:** Balancer Index token containing cbETH, cbBTC, NUT and SNUT.
{% endtab %}
{% endtabs %}

$pNUT offers an innovative solution for diversified, decentralized, and yield-generating exposure to multiple assets within the BASED NUT ecosystem. For further technical details and in-depth integration, refer to the ecosystem's technical paper.
