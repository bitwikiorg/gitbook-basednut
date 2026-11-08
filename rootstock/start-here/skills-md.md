# 🤹 Skills.md

{% prompt description="Rootstock Docs Skill" icon="head-side-gear" %}
```markdown
---
name: rootstock-docs
description: >
  Documentation skill for understanding and integrating ROOTSTOCK, a programmable root AMM on Base. Use for questions about Root Pools, liquidity provision, Root Pool Tokens, the Vault, Routers, swaps, hooks, fees, pool construction, integration flows, security boundaries, and protocol data.
metadata:
  version: "1.0"
  tags: [amm, defi, liquidity, base, rootstock, vault, pools, routers, hooks]
---

# ROOTSTOCK documentation skill

## Scope

Use these docs when the task concerns ROOTSTOCK protocol behavior, integration, extension, or analysis.

Do **not** infer deployment addresses, enabled factories, fee settings, governance permissions, or production feature availability from generic Balancer lineage. For exact deployed surfaces, use the current ROOTSTOCK deployment/reference pages or the canonical contract repository.

## Structural model

ROOTSTOCK separates responsibilities:

1. **Router** — receives user/application intent and composes workflows.
2. **Vault** — tracks token deltas, accounting, settlement, and shared liquidity operations.
3. **Root Pool** — defines market-specific mathematics and parameters.
4. **Hook** — optionally extends supported lifecycle points.
5. **Root Pool Token (RPT)** — represents proportional liquidity ownership.

## Decision rules

- If the user asks **what or why**, prefer `concepts/`.
- If the user asks **how to perform an operation**, prefer `integration-guides/`.
- If the user asks **how to create or extend protocol components**, prefer `build/`.
- If the user asks for **exact signatures, errors, events, addresses, ABIs, or contract surfaces**, prefer `developer-reference/`.
- If a claim depends on a live deployment, treat the deployment registry/code as more authoritative than conceptual prose.

## Core workflows

### Understand an LP position

Read, in order:
1. `concepts/liquidity/README.md`
2. `concepts/liquidity/root-pool-tokens.md`
3. `concepts/liquidity/fees-and-returns.md`
4. `concepts/liquidity/lp-risk-impermanent-loss.md`

### Understand a swap

Read:
1. `concepts/swaps/README.md`
2. `concepts/swaps/swap-lifecycle.md`
3. `concepts/routing/README.md`
4. `concepts/vault/accounting-settlement.md`

### Build a market

Read:
1. `concepts/pools/README.md`
2. the relevant pool family page;
3. `build/custom-pool.md` or `build/weighted-pool.md`;
4. `developer-reference/protocol-interfaces.md`;
5. deployment/reference material.

## Guardrails

- **Root Pool** means a market in ROOTSTOCK. **Rooted pool** means a weighted composition with one majority-weight asset. Do not conflate them.
- Do not describe RPT value as a fixed redemption amount; RPTs represent a share of a changing pool.
- Do not describe LP return as guaranteed yield.
- Do not describe hooks as replacing pool math or the Vault. Hooks extend configured lifecycle points.
- Do not assume all inherited Balancer pool types or routers are deployed in every ROOTSTOCK release.
- Distinguish price impact (caused by the trade) from slippage tolerance (the execution bound chosen by the caller).
- Distinguish pool swap fees, protocol fee shares, pool-creator fee shares, and external incentives.

```
{% endprompt %}

***

