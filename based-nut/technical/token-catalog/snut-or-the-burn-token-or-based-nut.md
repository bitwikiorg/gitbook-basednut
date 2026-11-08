# SNUT | The Burn Token | BASED NUT

Experimental Memefi

**SNUT is a liquid, non-escrow NUT reward-position token.** Hold SNUT in any wallet to automatically earn NUT rewards — no locking, no staking contract, no escrow. Every SNUT trade pays a ... tax that funds NUT rewards, buybacks, and liquidity. Buybacks send SNUT to the burn address, where it _keeps earning NUT_ — creating a recursive burn flywheel.

**Burn feeds burn.** Dead-held SNUT earns NUT. That NUT goes to dead too. The flywheel never stops. 🔥

| Metric       | Value |
| ------------ | ----- |
| Burned       | ...   |
| Circulating  | ...   |
| Price        | ...   |
| Buyback Fuel | ...   |

| Contract  | Address                                      |
| --------- | -------------------------------------------- |
| SNUT      | `0xac130701aa31c284c36609e2489f150f419ad7ad` |
| Dead      | `0x000000000000000000000000000000000000dEaD` |
| SNUT/ETH  | `0xB22895d2ee6e29395F30Ec47c8D9FE0d55355AE1` |
| SNUT/NUT  | `0x893faaa7baf7a8247fc7142afb28e13d51a5aae8` |
| Meta-pool | `0x82bbadb9d6b2c0a59ed01809e30323f89f6faa1c` |
| Balancer  | `0x2a5757b60987ff10385de1d4d923792f6fdcfff1` |

[📖 Docs](https://docs.basednut.com/snut)

## Market Stats

| Metric       | Value  |
| ------------ | ------ |
| Price        | ...    |
| Volume (24h) | ...    |
| Liquidity    | ...    |
| Total Supply | 0 SNUT |
| Circulating  | 0 SNUT |
| Buyback Fuel | 0 ETH  |
| Tax Rate     | ...    |

Total Supply, Circulating, and Buyback Fuel are read from Base RPC.

## 📊 Live Distribution

Where is all the SNUT right now? Live from Base blockchain.

* 🔥 Burned: **...** SNUT
* 🌊 In Pools: **...** SNUT
* 🌿 Free Float: **...** SNUT

## 🔥 Live Burn Tracker

| Metric                   | Value                                          |
| ------------------------ | ---------------------------------------------- |
| Burned to Dead Address   | ...                                            |
| Total Supply             | ... SNUT (from contract)                       |
| 💀 Dead-Held             | ... burned + still earning NUT                 |
| 🌿 Circulating           | ... in wallets + pools                         |
| 🔥 Dead-held SNUT/ETH LP | **...** Permanently locked — cannot be removed |

## 🔄 The Recursive Burn Flywheel

Every SNUT trade pays **...** tax. That tax becomes ETH. ETH buys NUT rewards and SNUT buybacks. Buyback SNUT goes to dead. Dead-held SNUT earns NUT rewards. Those NUT also go to dead. **Burn feeds burn. It never stops.**

{% stepper %}
{% step %}
### 🔄 SNUT Trade

buy or sell
{% endstep %}

{% step %}
### 💰 ... Tax Collected

auto-deducted on transfer
{% endstep %}

{% step %}
### ⚡ Swapback → ETH

tax SNUT sold for ETH
{% endstep %}

{% step %}
### 🔀 ETH Routes 4 Ways

rewards / buyback / liquidity / manager
{% endstep %}

{% step %}
### 🔥 Buyback SNUT → Dead

SNUT purchased and sent to burn address
{% endstep %}

{% step %}
### 💀 Dead-Held SNUT Earns NUT

dead address earns rewards by design
{% endstep %}

{% step %}
### 🔥 NUT Rewards → Dead

NUT sent to dead = NUT burned
{% endstep %}

{% step %}
### ♾️ Recursive Burn Compounds

dead share grows → more NUT to dead → more burn
{% endstep %}
{% endstepper %}

## 💰 Tax Breakdown (...)

Every SNUT transfer pays ... tax, split into 4 streams. Rates are read live from the smart contract.

| Stream            | Rate | Description                              |
| ----------------- | ---- | ---------------------------------------- |
| 💧 Auto Liquidity | ...  | SNUT/ETH LP created, some burned to dead |
| ⚙️ Manager Wallet | ...  | Operations and development               |
| 🔥 Buyback & Burn | ...  | Buys SNUT with ETH → sends to dead       |
| 🌰 NUT Rewards    | ...  | NUT bought and sent to SNUT holders      |

{% hint style="info" %}
**Swapback engine**: Tax SNUT is collected, sold for ETH, and routed to 4 destinations. Buyback fuel sits as ETH in the contract until triggered. Live fee values are read directly from the SNUT smart contract.
{% endhint %}

## 🌊 Four Pools, Four Roles

SNUT lives in multiple pools. Each has a different job — main liquidity, meta-market for LP rights, SNUT↔NUT venue, and multi-asset arbitrage surface.

### SNUT/ETH

**MAIN LIQUIDITY**

Primary market for SNUT. Price discovery happens here. LP token = claim on SNUT + ETH.

| Asset     | Value |
| --------- | ----- |
| SNUT      | ...   |
| ETH       | ...   |
| LP Burned | ...   |

Pool: `0xB22895d2ee6e29395F30Ec47c8D9FE0d55355AE1`

### SNUT-LP/ETH

**META**

Trade the LP token itself against ETH. Exit liquidity without removing it from the main pool.

| Asset    | Value |
| -------- | ----- |
| ETH      | ...   |
| LP Token | ...   |

Pool: `0x82bbadb9d6b2c0a59ed01809e30323f89f6faa1c`

### SNUT/NUT

**REACTOR**

Pairs the reward-position token directly against the root token — the primary SNUT↔NUT price venue.

| Asset | Value |
| ----- | ----- |
| SNUT  | ...   |
| NUT   | ...   |

Pool: `0x893faaa7baf7a8247fc7142afb28e13d51a5aae8`

### Balancer pNUT

**ARB BASKET**

Multi-asset pool: cbETH, SNUT, NUT, cbBTC. Arbitrage routing surface for the pNUT basket.

| Asset | Value |
| ----- | ----- |
| cbETH | ...   |
| SNUT  | ...   |
| NUT   | ...   |
| cbBTC | ...   |

Pool: `0x2a5757b60987ff10385de1d4d923792f6fdcfff1`

## 🏗️ Four Economic Layers

SNUT is not just a token. It is four economic mechanisms stacked into one liquid position.

{% stepper %}
{% step %}
### 🎁 Reward-Position

Hold SNUT, earn NUT. No locking, no escrow. Your wallet is your stake. The SNUT contract distributes NUT rewards to all holders proportional to their balance.
{% endstep %}

{% step %}
### 🔥 Burn Layer

Buybacks send SNUT to dead. Dead earns NUT. NUT sent to dead = NUT burned. Dead-held SNUT share grows over time, compounding the recursive burn.
{% endstep %}

{% step %}
### 🌴 Liquidity-Rights

SNUT/ETH LP = claim on pool assets. Meta-pool lets you trade that claim without exiting liquidity. LP token is a redeemable pro-rata claim on SNUT + ETH.
{% endstep %}

{% step %}
### ⚡ Arb Layer

Balancer = multi-asset arbitrage routing surface. SNUT/NUT = the direct SNUT↔NUT price venue.
{% endstep %}
{% endstepper %}

## 🧠 Common Misconceptions

| Misconception             | Reality                                               |
| ------------------------- | ----------------------------------------------------- |
| ❌ Escrow staking          | ✅ Non-escrow reward-position — your wallet, your keys |
| ❌ Supply burns literally  | ✅ Economic burn — SNUT sent to dead, still earns NUT  |
| ❌ Just a passive dividend | ✅ Recursive burn flywheel that compounds over time    |
| ❌ All pools are the same  | ✅ Each pool has a distinct economic purpose           |

[🔄 Trade on Uniswap](https://app.uniswap.org/explore/tokens/base/0xac130701aa31c284c36609e2489f150f419ad7ad) [🔍 Basescan](https://basescan.org/token/0xac130701aa31c284c36609e2489f150f419ad7ad) [🔥 Burn Transactions](https://basescan.org/token/0xac130701aa31c284c36609e2489f150f419ad7ad?a=0x000000000000000000000000000000000000dEaD#tokentxns) [📖 Docs](https://docs.basednut.com/snut)

_BASED NUT is an experimental memefi project. BASED NUT TOKENS are whimsical meme coins devoid of any intrinsic value or anticipation of financial gains. Coins are for entertainment purposes only. No formal team or roadmap. Please nut responsibly!_
