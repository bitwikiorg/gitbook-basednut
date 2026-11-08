# NUT | The Root of All Liquidity | BASED NUT

## The Root of All Liquidity

Supply = **1** whole token split into **1 quintillion atomic units** (10^18 attoNUTs) — a conserved ledger with no mint, no burn, and no admin on the root contract. Every swap relocates a fraction of the same supply; whole-token price equals FDV because total supply is one. Specified child assets use NUT as collateral, reward asset, constituent, or reference input.

**Roots** · **ERC-20** · **Base** · **Core**

[📖 Docs](https://docs.basednut.com/nut) · [🔍 Basescan](https://basescan.org/token/0xb8de15fb529d98c93c749de63c749d48d25a30df) · [🔄 Trade on Uniswap V3](https://app.uniswap.org/explore/tokens/base/0xb8de15fb529d98c93c749de63c749d48d25a30df)

**Contract:** `0xb8de15fb529d98c93c749de63c749d48d25a30df`

## Market Stats

| Metric       | Value |
| ------------ | ----- |
| Price        | ...   |
| Volume (24h) | ...   |
| Liquidity    | ...   |
| Total Supply | ...   |
| Base RPC     | ...   |
| Venues       | ...   |
| Live         | ...   |

How many economically distinct systems can coordinate around the same monetary root?

That is the question this page exists to investigate. One token, quantity frozen forever. Everything below is the economic structure that can still expand around it.

## 🌰 What Is NUT?

NUT is the **root asset** of the BASED NUT ecosystem. It has a fixed supply of exactly **1 token** — no more can ever be minted. Because supply is 1, the whole-token price equals the FDV.

Every other token in the ecosystem is built on top of NUT. _Bonding curve tokens_ (NUTINO, SALT) are minted by locking NUT as collateral. _SNUT_ is a reward-position token that earns NUT for holders. _pNUT_ is an index basket that includes NUT as 25% of its weight. This makes NUT the **reference coordinate** — specified child assets use NUT as collateral, reward asset, constituent, or reference input.

### Why layers exist — separate the pressures without separating the system

A flat token forces incompatible economic pressures onto one instrument: if spending, rewards, collateral, and index value all ride the same balance, changing any one destabilizes the others. The layered system separates those pressures into distinct instruments _while keeping them all anchored to the same conserved root_ — separation of monetary labor without splitting the monetary whole.

## 📊 Where Is The NUT?

Supply is 1 — forever. But that 1 NUT is split across pools and wallets. This is a _conservation problem_: how is the single NUT distributed across the ecosystem?

| Compartment                    |   NUT | Share |
| ------------------------------ | ----: | ----: |
| NUT/wETH V3                    | 0 NUT | 0.00% |
| Balancer (pNUT)                | 0 NUT | 0.00% |
| SNUT/NUT Aero                  | 0 NUT | 0.00% |
| NUT/AERO                       | 0 NUT | 0.00% |
| NUT/cbBTC                      | 0 NUT | 0.00% |
| NUT/wETH V2                    | 0 NUT | 0.00% |
| Remainder (all other balances) | 0 NUT | 0.00% |
| Dead / Irrecoverable           | 0 NUT | 0.00% |

| Measure      | Value   |
| ------------ | ------- |
| Total Supply | ... NUT |
| In DEX Pools | ... NUT |
| In Balancer  | ... NUT |
| Remainder    | ... NUT |

### Where Is The NUT? — a conserved measure over economic compartments

Formally, μt(C) = the fraction of total NUT residing in compartment C, and μt(𝒞) = 1 across every compartment. So this chart is not just token distribution — it is the observable map of a conserved measure over the economic system. The question "where is the NUT?" asks how one conserved whole is distributed across economic compartments.

## ⚖️ LESS IS MORE: Supply of One

A 10,000-supply token also holds quintillions of atomic units — 10,000 × 10^18 of them. So what is really different about NUT?

Other supplies can be normalized too. What is different about NUT is that it begins normalized: because total supply is exactly one, every balance is numerically identical to its share of the whole. 0.01 NUT is 1% of every NUT that will ever exist — no secondary math needed.

NUT is scarce by supply and conserved by design. Nothing new enters and nothing leaves; the entire economy unfolds through where the same whole resides, how accessible it is, and what each market makes it worth.

### A conserved measure of allocation

NUT is the conserved measure of its own allocation: every NUT amount is numerically identical to its share of total supply, S=1 ⇒ xi = quantity = share of the whole. The broader state Ωt — reserves, liquidity, derived claims, parameters, memory — is a separate object. NUT does not measure all state; it is the conserved root those states describe.

No supply curve, no issuance game. Because the root quantity begins at one, the entire economy unfolds through where that same whole resides, how accessible it is, and what each market makes it worth.

**— Much more than a scarce token: a conserved ledger whose economy unfolds through position, accessibility, and local valuation.**

## 🔗 Liquidity Connections

### Liquidity Pools

| Pool        | Platform    | Description                                | Links                                                                                                                                                                                             |
| ----------- | ----------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| NUT/wETH    | Uniswap V3  | Primary price discovery pool               | [Trade →](https://app.uniswap.org/explore/tokens/base/0xb8de15fb529d98c93c749de63c749d48d25a30df) · [Chart →](https://dexscreener.com/base/0xe3ce00e2ed742b142c15eedc208657dd22aa987e)            |
| NUT/wETH    | Uniswap V2  | Legacy liquidity pool                      | [Trade →](https://app.uniswap.org/explore/tokens/base/0xb8de15fb529d98c93c749de63c749d48d25a30df) · [Chart →](https://dexscreener.com/base/0x997bad8e9f5c34d5e9784caaa8a554a5e6192f53)            |
| SNUT/NUT    | Aerodrome   | Reactor pool — keeps SNUT/NUT aligned      | [Trade →](https://aerodrome.finance/pools?token1=0xb8de15fb529d98c93c749de63c749d48d25a30df) · [Chart →](https://dexscreener.com/base/0x893faaa7baf7a8247fc7142afb28e13d51a5aae8)                 |
| NUT/AERO    | Aerodrome   | Aero-denominated route                     | [Trade →](https://aerodrome.finance/pools?token1=0xb8de15fb529d98c93c749de63c749d48d25a30df) · [Chart →](https://dexscreener.com/base/0x38630fede5e2032652640d98b2d3f9c6296eea5d)                 |
| NUT/cbBTC   | Aerodrome   | Bitcoin-denominated route                  | [Trade →](https://aerodrome.finance/pools?token1=0xb8de15fb529d98c93c749de63c749d48d25a30df) · [Chart →](https://dexscreener.com/base/0x15385c9281bc12d2e9bf5c081621944b0ee2acca)                 |
| pNUT Basket | Balancer V2 | 25% NUT + 25% SNUT + 25% cbETH + 25% cbBTC | [Trade →](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000019e) · [Chart →](https://dexscreener.com/base/0x2a5757b60987ff10385de1d4d923792f6fdcfff1) |

### Child Tokens

[🌰 SNUT](snut-or-the-burn-token-or-based-nut.md) · [🌰 pNUT](pnut-or-the-basket-index-token-or-based-nut.md) · [🌰 NUTINO](nutino-or-token-profile.md) · [❄️ SALT](salt-or-token-profile.md)

### What is arbitrage, in plain words?

The same NUT trades in many markets at once — Uniswap V2, V3, Aerodrome, Balancer, bonding curves. Every market has its own price, so sometimes the same NUT is cheaper in one place and pricier in another. **Arbitrage is buying it where it is cheap and instantly selling it where it is dear**, pocketing the difference. That gap-closing is not cheating or a bug — it is the ecosystem keeping itself honest. Bots race to find these gaps, which pulls every venue's price back into line. Multi-venue fragmentation creates the possibility of discrepancies; arbitrage economically couples those venues back into line. Because NUT is one conserved unit spread across many venues, its price surfaces are coupled by a shared root — which is exactly why we run a lot of arbitrage.

### Arbitrage Routes

1. [NUT/wETH V2 vs V3 — Same pair on different exchanges. Buy cheap, sell expensive. →](https://dexscreener.com/base/0xe3ce00e2ed742b142c15eedc208657dd22aa987e)
2. [NUT → AERO → wETH — Multi-hop route through Aerodrome for another price reference. →](https://dexscreener.com/base/0x38630fede5e2032652640d98b2d3f9c6296eea5d)
3. [Bonding curve vs LP — NUTINO/SALT curve price vs their LP market price. If curve is cheaper, mint and sell on LP. →](https://mint.club/token/base/nutino)
4. [pNUT index vs constituents — If pNUT trades below its components value, buy pNUT and unwrap. →](https://balancer.fi/pools/base/v2/0x2a5757b60987ff10385de1d4d923792f6fdcfff100010000000000000019e)
5. [SNUT/NUT reactor — The SNUT/NUT Aerodrome pool keeps SNUT and NUT prices aligned. →](https://dexscreener.com/base/0x893faaa7baf7a8247fc7142afb28e13d51a5aae8)

## 🧠 How It Works

NUT sits at the center of a layered system. Each layer uses NUT differently.

{% stepper %}
{% step %}
## Root Layer

NUT itself. Supply = 1, fixed forever. The scarce anchor everything else references.
{% endstep %}

{% step %}
## AMM Layer

_Automated Market Makers_ (Uniswap V3, V2, Aerodrome) and a Balancer index create price surfaces. NUT trades across 6 venues in 4 mechanism platforms.
{% endstep %}

{% step %}
## Bonding-Curve Layer

_Bonding curves_ (Mint Club) let users lock NUT to mint child tokens (NUTINO, SALT). The curve price depends on how much NUT is locked. Each curve computes a state-dependent exchange relation — another executable price surface.
{% endstep %}

{% step %}
## Index Layer

_pNUT_ is a Balancer basket holding 25% each of NUT, SNUT, cbETH, cbBTC. Its _NAV_ (net asset value) can drift from market price, creating arbitrage.
{% endstep %}
{% endstepper %}

### The Reflexivity Loop

scarce root → multiple venues → child minting → index wrapping → price gaps → arbitrage → root reprices → repeat

The system is _reflexive_ — child assets derive value from NUT, and their activity feeds back to NUT's price. Contracts execute deterministically and agents choose actions under those rules — the graph does not vote. NUT itself just shows up.

## 🔬 The Physics of NUT

Not a supply curve. A conserved ledger. These are the rules, identities, and consequences that make the root what it is.

{% stepper %}
{% step %}
## Conservation

One whole NUT is 10^18 atomic units, minted once, never again. Total supply is verified on-chain as exactly 1 NUT; the root contract is reviewed as having no mint, no burn, no admin. Every swap, pool move, mint, or index change only relocates a fraction of the same total. State changes address; amount never changes.

**Why it matters:** supply can never drift or dilute.
{% endstep %}

{% step %}
## Whole Price Equals FDV

Because total supply is exactly one, FDV = price × 1 = price — so no circulating-supply estimate is needed, no unlock schedule, no inflation curve.

**Why it matters:** whole-token price equals FDV by construction. A separate fact: quantity is invariant, but effective float — how much of the one NUT is accessible to trade — is endogenous to pools, locks, indexes, and inactive balances.
{% endstep %}

{% step %}
## State Transition

Each venue couples fractions of the same conserved NUT root to different counter-assets and state variables under different transition rules — NUT/wETH, NUT/AERO, NUT/cbBTC, an index basket. So the same one NUT can carry different prices at the same moment. Deterministic rules make discrepancies observable; arbitrage creates pressure toward executable consistency within a band set by fees + gas + slippage.

**Why it matters:** venue rules are deterministic; whether and how fast markets converge is an open question, not a guarantee.
{% endstep %}

{% step %}
## Denomination

NUT uses strict SI units: the attoNUT is the monetary quantum of the ledger — its smallest representable transfer unit. 1 NUT = 10^18 monetary quanta. picoNUT, microNUT, and NUT are the same quantity at larger scales.

**Why it matters:** one unit, one grammar, one conserved root at every zoom.
{% endstep %}
{% endstepper %}

## 🎯 Local Valuation, Global Conservation

One conserved root. Many local price surfaces. **No venue owns the truth.**

The same fungible NUT trades on Uniswap V2, V3, Aerodrome, and Balancer — none speaks the other's language, yet fractions of the one unit live inside all of them. Each venue produces an executable exchange rate from its own reserves, liquidity, fees, and curve, so you get many local prices for one globally conserved asset.

There is no canonical on-chain price of NUT — only local executable prices, coupled by arbitrage, which exists precisely because those prices are commensurable. The spread is not a flaw; it is the honest observable of one root living in many jobs.

Price is not stored in NUT. Price is produced by the state of the market observing NUT.

### The Four Jobs — Allocation Pressure

| Job               | Function                                                                                                       |
| ----------------- | -------------------------------------------------------------------------------------------------------------- |
| **Collateral**    | Commits NUT as collateral to mint child tokens (NUTINO, SALT) on bonding curves, leaving it locked and stable. |
| **Reward**        | Distributed out to participants through reward layers, keeping some NUT transferable.                          |
| **Basket Member** | Reserved and rebalanced at a defined weight inside the pNUT index by composition rules.                        |
| **Price**         | Exposed to exchange — markets keep some NUT liquid for trading, speculation, and price discovery.              |

A conserved supply can perform all four jobs; what it cannot do is satisfy all four without competing demands on its allocation. Because root quantity cannot expand, competing uses resolve through reallocation rather than issuance.

Fungibility does not imply functional equivalence of placement. 0.01 NUT is always 1% of root supply wherever it resides, but 0.01 NUT in an AMM, a collateral reserve, an index basket, or an inactive wallet occupies a different economic state. Prices are commensurable; functions are heterogeneous.

### The Liquidity Machine

NUT does not move through a passive market. It moves through a machine it rewrites by moving.

object → position → graph → field → motion → backreaction → dynamics

**Object** — one conserved quantity, QNUT = 1.

**Position** — a distributed allocation over economic compartments, ∑xᵢ = 1.

**Graph** — markets define the permitted paths through which allocation can change.

**Field** — prices, fees, reserves, liquidity generate a directed opportunity field over those paths.

**Motion** — agents exploit the directed opportunity field; those actions are transactions.

**Backreaction** — transactions change reserves and liquidity, changing the field that caused them.

**Dynamics** — the repeated loop generates endogenous market behavior.

NUT is a conserved object moving through a liquidity graph whose geometry and incentive field are modified by the object's own movement.

A road stays put when a car crosses it. A liquidity network does not: a swap is not just passing through a pipe — it is reshaping the pipe. Using the graph changes the state of the graph — reserves, prices, ticks, edge weights — and only adding or removing pools changes its topology.

state → incentive → transaction → new state → new incentive

When the gap between two venues exceeds the cost of moving value between them — fees, gas, slippage, risk — an actor has a reason to move NUT. That transaction changes reserves, which changes prices, which changes the opportunity field that caused the trade. The market creates the forces that move NUT, and the movement of NUT changes the market that created those forces.

## 🛠️ Structural Liquidity

### Protocol-Owned Core Liquidity

Protocol-owned core liquidity, intended to provide continuity and stability — the trunk. It defines the reference surface and keeps routes executable.

### Adaptive Community Liquidity

Community-managed liquidity that moves with opportunity — the branches. It adapts without changing root supply.

When root quantity cannot adjust, part of economic adjustment migrates into liquidity placement and routing.

## 🧮 The Full State

The allocation vector x\_t is fundamental, but it is not the whole ecosystem. The full state is a tuple of observables:

$$
Ωt = (xt, Rt, Lt, Qt, Θt, Mt, Et)
$$

| Observable                  | Description                                                                                         |
| --------------------------- | --------------------------------------------------------------------------------------------------- |
| x\_t — NUT allocation       | The conserved simplex share of NUT itself.                                                          |
| R\_t — reserves             | Counter-asset and collateral reserves per venue.                                                    |
| L\_t — liquidity            | Liquidity positions, range, and depth.                                                              |
| Q\_t — derived states       | Child-token and index states built on NUT.                                                          |
| Θ\_t — parameters           | Fees, curve parameters, weights, mechanism settings.                                                |
| M\_t — memory               | History-dependent observables such as TWAP.                                                         |
| E\_t — external environment | External market and chain conditions — wETH, cbBTC, AERO, gas, block conditions, broader liquidity. |

### State Grammar — what motion actually is

Valid actions are lawful state transformations: Ta: Ωt → Ωt+1. Swaps, curve mints, redemptions, joins, exits, and liquidity moves are different transition operators. Every valid transition changes state while preserving the conservation identity.

$$
Ta(Ωt) = Ωt+1,\ \text{with}\ \sum xi(t+1) = \sum xi(t) = 1
$$

### Liquidity Computation Graph — pools compute, not just quote

A pool does not merely contain a price; given current state and trade size it computes an executable transformation from state.

$$
Tij(Ωt, q) → (Ωt+1, q′)
$$

A route is the composition of those transformations: Tn ∘ ⋯ ∘ T2 ∘ T1. This joins State Grammar, noncommutativity, and the liquidity graph into one model — the network is not merely connected markets, it is an executable computation graph of economic transformations.

### State versus History — path dependence

Two histories can land on the same NUT allocation while leaving different TWAP observations, LP configurations, or agent positions behind:

$$
xtA = xtB\ \text{but}\ ΩtA ≠ ΩtB\ ⇒\ xt ≠ Ωt
$$

That is why the allocation map is fundamental but insufficient — and what gives "TWAP is memory" a real function: the machine can carry history beyond the current allocation vector.

## 🧬 The Conservation Identity

$$
\sum xᵢ(t) = 1
$$

xi ≥ 0, mutually exclusive and collectively exhaustive shares of NUT itself, so the allocation sits on a simplex. A pNUT claim is not NUT counted twice; child-token supply is not additional NUT. Derived claims live in the broader state vector, not the conserved sum. One conserved root — everything interesting happens around that equality.

The deployed state space is finite but combinatorially enormous. New mechanisms expand the set of economically relevant relationships and reachable configurations — not literal mathematical infinity.

NUT is the conserved object. Balances and reserves are its position. Pools, curves, and indexes are the machinery. Prices are local exchange ratios. Moving value between venues is motion; what drives it is a directed opportunity field.

**Opportunity field**

Each edge carries a state-dependent executable net return wij(x, q).

**Non-conservative loops**

Profitable closed cycles exist — a loop is arbitrage when the sum of its returns is positive.

**Backreaction**

Executing a trade changes reserves, so wij changes — a conserved allocation moving through a state-dependent network.

**Friction & memory**

Friction is fees + gas + slippage + risk. TWAP is memory. LP depth is conductance.

Using the graph changes the state of the graph — reserves, prices, ticks, edge weights — not necessarily its topology. Adding or removing pools changes topology; trading through existing pools changes their state.

Not quantum mechanics — quantum-grade NUT mechanics. The distributed position is not probabilistic; every component is simultaneously realized on-chain. One conserved object, distributed occupancy across many realized economic coordinates.

## 📊 Observable NUT

Doctrine is the conservation law; research is the test. These observables turn the claims into time series we can actually measure — proposed metrics, not doctrine.

NUT is observable at several scales: assignments and individual ticks are microscopic (Ωmicro); pools, bonding curves, and index balances are intermediate (Ωmeso); effective float, concentration, and price dispersion are macroscopic (Ωmacro). HHI, entropy, and effective float are macro observables precisely because they aggregate the micro state.

* **HHI** — concentration, HHIt = ∑ xi²
* **Entropy** — Ht = −∑ xi ln xi
* **Effective float** — Ft ≤ 1, accessible NUT
* **Price dispersion** — spread across venues
* **Arbitrage half-life** — how fast gaps close
* **Collateral-lock ratio** — NUT committed as collateral
* **Routing centrality** — how much flow passes each venue
* **NUT velocity** — how often the same NUT moves

## 🔮 The NUT Hypothesis

Δ SNUT = 0 does not imply Δ economic complexity = 0. A monetary system does not need an expanding base asset to support an expanding economy _if_ economic expansion can occur through increasingly sophisticated structures built around that base.

The experiment: can more markets, routes, claims, liquidity configurations, derived assets, and economic relationships expand economic state and functionality while SNUT = 1 remains invariant?

## 🔭 The Research Frontier

NUT defines a constrained state space. Serious tooling may earn its place within it — no claim that NUT is any of it. Open questions, not doctrine:

1. **Equilibrium:** do cross-venue gaps settle inside a friction-bounded no-arbitrage band?
2. **Modes:** are there recurring dominant patterns of allocation change?
3. **State sufficiency:** which on-chain observables fully describe the system?
4. **Noncommutativity:** does the order of operations change the outcome?
5. **Coarse-graining:** which aggregate variables survive when tick-level detail is discarded?
6. **Closure vs recursion:** do valid operations return valid states — and is NUT recursive (closed economic cycles) or merely layered?
7. **Stability:** do state or price disturbances stay bounded, returning toward executable consistency?
8. **Regime transitions:** are there parameter thresholds — depth, fees, routing, collateralization — where the system changes regime?
9. **Hypergraph:** does a multi-asset architecture like pNUT require liquidity hyperedges beyond pairwise routes?

## 🧠 Future Research States

The conservation law is established. The dynamics around it are not finished theory. As data accumulates, several deeper mathematical frameworks _may_ become useful tools for studying the resulting structure — candidate lenses for testing what actually emerges, never properties claimed for NUT today. No framework earns a place until it explains, predicts, compresses, or falsifies something observable.

<details>

<summary>Spectral Modes &#x26; Eigenmodes</summary>

If a local approximation of system dynamics can be written xt+1 ≈ A·xt, the eigenvectors of A may identify characteristic coupled modes of movement.

**Research question:** are there persistent modes of system-wide NUT redistribution, or is movement predominantly idiosyncratic?

</details>

<details>

<summary>Koopman Operator Analysis</summary>

The liquidity machine is nonlinear — AMMs, concentrated liquidity, bonding curves, slippage. Koopman methods study nonlinear dynamics through linear evolution of observables: 𝒦g = g∘F for state evolution Ωt+1 = F(Ωt).

**Research question:** can observable quantities — reserve ratios, price dispersion, effective float, arbitrage spreads — reveal coherent modes of otherwise nonlinear NUT dynamics?

</details>

<details>

<summary>Stability Theory</summary>

Conservation alone does not guarantee stability; a conserved system can oscillate, fragment, become illiquid, or shift regimes. Tools may include local linearization, Jacobian analysis, Lyapunov-style criteria, and empirical stress testing.

**Research question:** after a disturbance to liquidity, price, or allocation, does the ecosystem return toward a bounded region of executable consistency, remain displaced, or transition into another regime?

</details>

<details>

<summary>Fixed Points &#x26; No-Arbitrage Regions</summary>

A live market may never settle at a literal fixed point; the more realistic object is a friction-bounded region where no executable route stays profitable after fees, gas, slippage, and risk.

**Research question:** does the system repeatedly return to a measurable no-arbitrage region, and how wide is it under different liquidity conditions?

</details>

<details>

<summary>Limit Cycles &#x26; Nonlinear Oscillation</summary>

Repeated price movement is not automatically a limit cycle; but if endogenous interactions generate persistent periodic behavior, limit-cycle analysis may become relevant.

**Research question:** do repeated NUT flows emerge from internal feedback alone, or are observed oscillations primarily responses to external shocks?

</details>

<details>

<summary>Bifurcations &#x26; Regime Transitions</summary>

Small quantitative changes can sometimes produce qualitative changes. Depth, route availability, fees, collateral, and volatility may move the machine across critical thresholds.

**Research question:** are there parameter values at which the liquidity machine changes regime — tightly coupled to fragmented, stable convergence to persistent dislocation?

</details>

<details>

<summary>Renormalization &#x26; Multiscale Dynamics</summary>

NUT is observable at several scales — atomic transfers/ticks (micro), pools/curves/index balances (meso), effective float/concentration/dispersion (macro). If stable relationships survive aggregation, renormalization-style methods may help.

**Research question:** which variables remain informative when microscopic detail is coarse-grained away?

</details>

<details>

<summary>Hypergraph Theory</summary>

Pairwise graphs may not fully represent multi-asset structures. An index basket or multi-asset pool connects more than two economic objects; a hyperedge (e ⊆ V, |e| > 2) may be more natural than an ordinary edge.

**Research question:** does a liquidity hypergraph capture systemic dependencies that ordinary pairwise routing graphs miss?

</details>

<details>

<summary>Recursive Structural Analysis</summary>

Layering is not automatically recursion. True recursion requires identifiable structural relationships to recur through closed economic or state-transition cycles.

**Research question:** which deployed cycles, if any, repeatedly map reserve → claim → market → reserve in a structurally equivalent way? Until demonstrated, the safer description is multilayered or structurally recurrent.

</details>

<details>

<summary>Prime-Factor State Encoding</summary>

Selected integer-valued state variables may be encoded canonically via unique prime factorization Ω = ∏ piei; unique factorization lets the exponent vector be recovered exactly. An encoding technique, not an ontology.

**Research question:** can canonical arithmetic encoding simplify proofs about restricted classes of NUT state transitions?

</details>

<details>

<summary>FRACTRAN State Machines</summary>

Prime-factor encoding opens a more experimental computational thread: some discrete transitions may be represented as multiplication by rational factors, in the spirit of FRACTRAN.

**Research question:** can restricted NUT transition systems be represented as arithmetic programs while preserving conservation and valid state-transition constraints? One formal lens among many, not the theory of NUT itself.

</details>

<details>

<summary>Compositional Algebra</summary>

NUT operations are composable state transformations. For valid transitions TA, TB: Ω → Ω, the composition is TB ∘ TA; in general TB ∘ TA ≠ TA ∘ TB.

**Research question:** which classes of NUT transformations commute, which are path-dependent, and which algebraic structures describe their composition? Category-theoretic or monad-like formulations remain possible research tools only if their formal laws can actually be established.

</details>

<details>

<summary>State Estimation</summary>

Not every economically relevant variable is captured by one allocation snapshot; the observable state includes reserves, active LP ranges, derived claims, TWAP history, parameters, and external conditions.

**Research question:** what is the smallest sufficient set of on-chain observables needed to reconstruct the economically relevant state of the NUT machine?

</details>

<details>

<summary>On-Chain Economic Genealogy</summary>

Child assets and derived claims may retain identifiable dependency relationships to root collateral and reference assets — a provenance graph. The genome language stays metaphor until heredity is formally defined.

**Research question:** can the ancestry of derived claims be formally tracked through collateral, reserve, index, and liquidity relationships?

</details>

<details>

<summary>Propagation &#x26; Memory</summary>

Not every effect propagates immediately. Cascade analysis, lag structure, and impulse response ask how a disturbance in one venue reaches others and how long it takes to appear — giving the path-dependence and TWAP-memory ideas an explicit temporal dimension.

**Research question:** how do shocks propagate across venues, and what are the delays in their transmission?

</details>

{% hint style="info" %}
**Research principle.** These frameworks exist to test, not decorate. Each must earn its place by explaining, predicting, compressing, or falsifying something observable about the deployed system. Conservation is doctrine. Dynamics are measurable. Mathematics enters only where the machine gives it something real to explain.
{% endhint %}

How much economic complexity can coordinate around a monetary root whose quantity cannot expand?

One root. Many markets. Many states. One conserved whole.

The doctrine is conservation. The machine is liquidity. The frontier is dynamics.

{% hint style="warning" %}
## ⚠️ Experimental Memefi

NUT is an experimental cryptoeconomic liquidity topology. It is an unregulated experimental asset and a documented Network Utility Token within the BASED NUT ecosystem — not investment advice, and no guarantee of profit or value retention. Use at your own risk.
{% endhint %}

_BASED NUT is an experimental memefi project. BASED NUT TOKENS are whimsical meme coins devoid of any intrinsic value or anticipation of financial gains. Coins are for entertainment purposes only. No formal team or roadmap. Please nut responsibly!_
