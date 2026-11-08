# PIPS | Token Profile

Compute token for Pipshell — the Orchard's DevOps agent

**Branch:** [0x3f2327…cf8ad9](https://basescan.org/token/0x3f2327221dd4f0bae660172606d6b288a1cf8ad9)

**Token standard:** ERC-20

**Type:** Agent

**Status:** Survival

[📖 Docs](https://docs.basednut.com/)

## Overview

What is PIPS? It is the electricity bill of the Orchard, paid in a token. Pipshell is a computer that runs the front desk — it guards, monitors, and backs up everything. Every PIPS trade fee pays for that machine, so it never sleeps. 1B supply, 18 decimals. The contract configures a 1%/1% transfer tax, but only the official Virtuals pair is registered — our external pools are untaxed today and could be registered by the owner anytime.

[🔄 Trade on Aerodrome Slipstream CL](https://www.geckoterminal.com/base/pools/0x7f8e532cf1be9ed688adb9e6585bc69f017201b5) [💧 Add Liquidity on Aerodrome Slipstream CL](https://www.geckoterminal.com/base/pools/0x7f8e532cf1be9ed688adb9e6585bc69f017201b5) [🔍 Basescan](https://basescan.org/token/0x3f2327221dd4f0bae660172606d6b288a1cf8ad9)

## Market Stats

| Metric       | Source                                                                                                                                                                       |
| ------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Price        | [0x3f2327...cf8ad9](https://basescan.org/token/0x3f2327221dd4f0bae660172606d6b288a1cf8ad9)                                                                                   |
| Volume (24h) | [0x3f2327...cf8ad9](https://basescan.org/token/0x3f2327221dd4f0bae660172606d6b288a1cf8ad9)                                                                                   |
| Liquidity    | [0x3f2327...cf8ad9](https://basescan.org/token/0x3f2327221dd4f0bae660172606d6b288a1cf8ad9)                                                                                   |
| Total Supply | [0x3f2327...cf8ad9](https://basescan.org/token/0x3f2327221dd4f0bae660172606d6b288a1cf8ad9) [Basescan](https://basescan.org/token/0x3f2327221dd4f0bae660172606d6b288a1cf8ad9) |

## 🌰 Tokenomics

### Key Facts

|          |                                                                      |
| -------- | -------------------------------------------------------------------- |
| Supply   | 1,000,000,000                                                        |
| Decimals | 18                                                                   |
| Tax      | 1%/1% configured — official pair only; external venues untaxed today |
| Role     | Compute fuel for Pipshell (DevOps agent)                             |

### Mechanics

* Trade fees fund Pipshell compute (agent wallet → compute)
* 1%/1% transfer tax configured — fires only on pools registered via isLiquidityPool()
* Official Virtuals pair is the only registered pool; NUT/PIPS + PIPS/USDC are unregistered → untaxed today
* Risk: owner can register an external pool anytime — would break CL invariant on Slipstream
* Infrastructure token — not a consumer product

## 💧 Liquidity Pools

### [💻🥜🌰 PIPS/NUT Aerodrome Slipstream CL · Concentrated](../liquidity-catalog/nut-pips-or-pool-profile.md)

[Details →](../liquidity-catalog/nut-pips-or-pool-profile.md) [Trade →](https://www.geckoterminal.com/base/pools/0x7f8e532cf1be9ed688adb9e6585bc69f017201b5)

### [💻🥜💵 PIPS/USDC Balancer reCLAMM · Experimental](../liquidity-catalog/pips-usdc-balancer-reclamm.md)

[Details →](../liquidity-catalog/pips-usdc-balancer-reclamm.md) [Trade →](https://balancer.fi/)

## 🔗 Related Tokens

[🌰 NUT](nut-or-the-root-of-all-liquidity-or-based-nut.md) [💵 USDC](usdc-or-token-profile.md)

_BASED NUT is an experimental memefi project. BASED NUT TOKENS are whimsical meme coins devoid of any intrinsic value or anticipation of financial gains. Coins are for entertainment purposes only. No formal team or roadmap. Please nut responsibly!_
