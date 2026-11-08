# pNUT | The Basket Index Token | BASED NUT

## The Basket Index Token

A **Balancer Weighted Pool** holding 25% each of NUT, SNUT, cbETH, and cbBTC. pNUT is the _BPT_ (Balancer Pool Token) that represents proportional ownership of the entire basket.

|              |             |
| ------------ | ----------- |
| Basket Index | Balancer V2 |
| Network      | Base        |
| Weights      | 25/25/25/25 |

[📖 Balancer Pool](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000000019e) [🔍 Basescan](https://basescan.org/token/0x2a5757b60987ff10385de1d4d923792f6fdcfff1)

**BPT Contract:**

`0x2a5757b60987ff10385de1d4d923792f6fdcfff1`

## 📊 Pool Metrics

The Balancer implied price is derived from the pool's internal balances and external price feeds. This pool alone should not decide price — it relies on its internal mechanics to force arbitrage. Treat it as an _endogenous state sensor_ inside a reflexive AMM network, not as an exogenous truth oracle.

| Metric                 | Source              |
| ---------------------- | ------------------- |
| Balancer implied price | Base RPC + Balancer |
| NAV (raw)              | Balances × prices   |
| Total Liquidity        | Balancer Vault      |
| BPT Supply             | Base RPC            |

## 🥜 What Is pNUT?

pNUT is a **basket index token** — a _BPT_ (Balancer Pool Token) that represents proportional ownership of a Balancer _weighted pool_ containing four assets: NUT, SNUT, cbETH, and cbBTC, each targeting 25% weight.

The pool uses a _constant-mean AMM_ (Automated Market Maker) — Balancer's weighted-pool math that maintains the 25/25/25/25 target ratio through trading activity. pNUT converts NUT from a **singleton meme-root** into a **basketized liquidity index**, coupling it with blue-chip reserve assets (cbETH = Coinbase ETH, cbBTC = Coinbase BTC).

## 📊 Basket Composition

Live weights of all 4 constituents. Target is 25% each — actual weights drift as prices change.

## 🧠 How It Works

pNUT is powered by Balancer's weighted-pool mechanics. Here is how the basket maintains its target ratios.

{% stepper %}
{% step %}
### Constant-Mean AMM

Balancer's _weighted pool_ uses a constant-mean invariant — the geometric weighted mean of token balances stays constant. This targets 25/25/25/25 but lets weights drift as prices move, creating natural rebalancing through trades.
{% endstep %}

{% step %}
### BPT Valuation

_BPT_ value = (underlying balances × market prices) / total BPT supply. Balancer explicitly warns this is **informational and manipulable** if naively used as an on-chain oracle. For safer on-chain valuation: use _getActualSupply()_ (not raw totalSupply), check Vault reentrancy, and use invariant-based weighted-pool valuation rather than raw balance × price.
{% endstep %}

{% step %}
### NAV Arbitrage

If BPT market price drifts from _NAV_ (Net Asset Value — the sum of underlying values per BPT), arbitrageurs mint or redeem BPT to restore parity. This keeps pNUT priced close to its intrinsic basket value.
{% endstep %}

{% step %}
### Forced Coherence

The basket creates _arbitrage pressure_ linking NUT ecosystem tokens with blue-chip reserves. When NUT or SNUT drift in weight, traders swap them in or out of the pool, connecting their prices to cbETH and cbBTC markets.
{% endstep %}
{% endstepper %}

## 🔗 Connections

### Constituent Tokens

### Balancer Pool

[Balancer V2 Weighted Pool 25% NUT + 25% SNUT + 25% cbETH + 25% cbBTC →](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000000019e)

### Arbitrage Routes

{% stepper %}
{% step %}
### BPT vs NAV

Mint/redeem BPT when market price diverges from intrinsic NAV (underlying values per BPT).
{% endstep %}

{% step %}
### Constituent vs Basket

If NUT weight drifts high, swap NUT into pool, arbitrage vs external NUT pools (Uniswap V3, Aerodrome).
{% endstep %}

{% step %}
### SNUT weight drift

SNUT overweight → swap SNUT in, sell externally; underweight → buy externally, add to pool.
{% endstep %}

{% step %}
### Cross-pool

NUT in Balancer vs NUT in Uniswap V3 — pNUT basket creates additional arbitrage pressure on NUT price.
{% endstep %}
{% endstepper %}

## 📐 Advanced: Root-Indexed Constant-Mean Market Maker

pNUT couples endogenous network assets with exogenous reserves in a reflexive AMM. The following is theoretical analysis, not financial advice.

### Root-Indexed AMM

pNUT couples _endogenous_ network assets (NUT, SNUT) with _exogenous_ reserve assets (cbETH, cbBTC) in a reflexive AMM network. The basket's invariant links internal scarcity dynamics to external market prices.

### Basketized Liquidity Index

pNUT converts NUT from a _singleton meme-root_ into an _indexable market object_ with forced coherence — the pool's constant-mean invariant continuously pushes weights toward target.

### Not an Oracle

The pool encodes useful internal market state, but it is **not an oracle**. Because it contains both exogenous reserves (cbETH, cbBTC) and endogenous ecosystem assets (NUT, SNUT), its spot prices and naive BPT NAV are **manipulable via forced trading** and circular when used as price truth. The pool is an _endogenous state sensor_ — it reflects what is happening inside the AMM, not what the true external price is.

### Forced Rebalancing Pressure

The _constant-mean invariant_ creates continuous rebalancing pressure that links NUT's scarcity dynamics to blue-chip crypto markets. Every trade in the pool moves weights, and every weight gap is an arbitrage opportunity.

### Price Truth Comes From Outside

Do **not** use this pool as a price oracle. If you need reliable price discovery, use **external sources**: external price feeds for exogenous assets (cbETH, cbBTC), multi-venue TWAP/median aggregation from _other_ DEXes (Uniswap V3, Aerodrome) for endogenous assets (NUT, SNUT). The pool's role is to reflect internal AMM state, not to dictate external prices. Any on-chain integration should use invariant-based BPT valuation with _getActualSupply()_, Vault reentrancy checks, liquidity thresholds, and circuit breakers — treating the pool as a state sensor, never as truth.

### Research Questions pNUT Tests

1. Can a basket index enforce topological monetary policy without governance?
2. Do LPs in a weighted pool act as constitutional actors in the basket?
3. Can TWAP in a weighted pool serve as memory for the basket index?
4. Is there reflexivity between the NUT singleton and the pNUT basket index?
5. Does forced coherence between meme-root and blue-chip reserves create stable pricing?

{% hint style="warning" %}
### Experimental Memefi

pNUT is a cryptoeconomic basket index experiment. The Balancer implied price is informational and manipulable — do not use it as a standalone price oracle. Not a utility token. Not a security. No guarantee of profit or value retention. Use at your own risk.
{% endhint %}

_BASED NUT is an experimental memefi project. BASED NUT TOKENS are whimsical meme coins devoid of any intrinsic value or anticipation of financial gains. Coins are for entertainment purposes only. No formal team or roadmap. Please nut responsibly!_
