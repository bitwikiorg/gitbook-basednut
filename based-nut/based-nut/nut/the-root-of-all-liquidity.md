# 🌰 The Root of All Liquidity

{% hint style="danger" %}
### **WARNING: YOU ARE READING ADVANCED NUT THEORY**

Advanced theory is math theater, a cosplay for marketing people who thought the whitepaper needed more symbols. Several pages of mathematics follow to explain why **1 NUT = the entire supply**. We apologize for the inconvenience.
{% endhint %}

<figure><img src="../../.gitbook/assets/image (14).png" alt="" width="563"><figcaption></figcaption></figure>

{% hint style="info" %}
## NUT

One whole token split into 1 quintillion atomic units (10^18 attoNUTs) — a conserved ledger with no mint, no burn, and no admin on the root contract.



Every swap relocates a fraction of the same supply; whole-token price equals FDV because total supply is one.



Specified child assets use NUT as collateral, reward asset, constituent, or reference input.
{% endhint %}

### The Master Question

> How many economically distinct systems can coordinate around the same monetary root?

One token, quantity frozen forever. Everything in this ecosystem is the economic structure that can still expand around it.



NUT is the **root asset** of the BASED NUT ecosystem. Because supply is 1, the whole-token price equals the FDV. Every other token in the ecosystem is built on top of NUT:

* **Bonding curve tokens** (NUTINO, SALT) are minted by locking NUT as collateral
* **SNUT** is a reward-position token that earns NUT for holders
* **pNUT** is an index basket that includes NUT at 25% weight

This makes NUT the **reference coordinate** — child assets use NUT as collateral, reward asset, constituent, or reference input.



### Why Layers Exist

A flat token forces incompatible economic pressures onto one instrument: if spending, rewards, collateral, and index value all ride the same balance, changing any one destabilizes the others.&#x20;

The layered system separates those pressures into distinct instruments **while keeping them all anchored to the same conserved root** — separation of monetary labor without splitting the monetary whole.



### A Conserved Measure of Allocation

Supply is 1 — forever. But that 1 NUT is split across pools and wallets. This is a **conservation problem**: how is the single NUT distributed across the ecosystem?

Formally: μ(C) = the fraction of total NUT residing in compartment C, and μ(𝒞) = 1 across every compartment. "Where is the NUT?" is not just token distribution — it is the observable map of a **conserved measure** over the economic system.



#### Normalized by Construction

A 10,000-supply token also holds quintillions of atomic units — so what is really different about NUT? Other supplies can be normalized too.

What is different is that NUT **begins normalized**: because total supply is exactly one, every balance is numerically identical to its share of the whole. 0.01 NUT is 1% of every NUT that will ever exist — no secondary math needed.



***

### The Four Rules

#### 1 — Conservation

One whole NUT is 10^18 atomic units, minted once, never again. Total supply is verified on-chain as exactly 1 NUT; the root contract has no mint, no burn, no admin. Every swap, pool move, mint, or index change only relocates a fraction of the same total. **State changes address; amount never changes.**

_Why it matters:_ supply can never drift or dilute.



#### 2 — Whole Price Equals FDV

Because total supply is exactly one, FDV = price × 1 = price — no circulating-supply estimate needed, no unlock schedule, no inflation curve. A separate fact: quantity is invariant, but **effective float** — how much of the one NUT is accessible to trade — is endogenous to pools, locks, indexes, and inactive balances.

_Why it matters:_ whole-token price equals FDV by construction.



#### 3 — State Transition

Each venue couples fractions of the same conserved NUT root to different counter-assets and state variables under different transition rules — NUT/wETH, NUT/AERO, NUT/cbBTC, an index basket. The same one NUT can carry different prices at the same moment. Deterministic rules make discrepancies observable; arbitrage creates pressure toward executable consistency within a band set by fees + gas + slippage.

_Why it matters:_ venue rules are deterministic; whether and how fast markets converge is an open question, not a guarantee.



#### 4 — Denomination

NUT uses strict SI units: the attoNUT is the monetary quantum of the ledger — its smallest representable transfer unit. 1 NUT = 10^18 monetary quanta. picoNUT, microNUT, and NUT are the same quantity at larger scales.

_Why it matters:_ one unit, one grammar, one conserved root at every zoom.



***

### The Four Jobs — Allocation Pressure

<table><thead><tr><th width="171">Job</th><th>What it does</th></tr></thead><tbody><tr><td><strong>Collateral</strong></td><td>Commits NUT to mint child tokens (NUTINO, SALT) on bonding curves — locked and stable</td></tr><tr><td><strong>Reward</strong></td><td>Distributed to participants through reward layers — keeping some NUT transferable</td></tr><tr><td><strong>Basket Member</strong></td><td>Reserved and rebalanced at a defined weight inside index and lp positions.</td></tr><tr><td><strong>Price</strong></td><td>Exposed to exchange — markets keep some NUT liquid for trading and price discovery</td></tr></tbody></table>

A conserved supply can perform all four jobs; what it cannot do is satisfy all four without competing demands on its allocation. Because root quantity cannot expand, competing uses resolve through **reallocation rather than issuance**.

Fungibility does not imply functional equivalence of placement: 0.01 NUT is always 1% of root supply wherever it resides, but 0.01 NUT in an AMM, a collateral reserve, an index basket, or an inactive wallet occupies a different economic state. **Prices are commensurable; functions are heterogeneous.**



***

### The Liquidity Machine

NUT does not move through a passive market. It moves through a machine it rewrites by moving:

> **object → position → graph → field → motion → backreaction → dynamics**

* **Object** — one conserved quantity, Q\_NUT
* **Position** — a distributed allocation over economic compartments, ∑xᵢ = 1
* **Graph** — markets define the permitted paths through which allocation can change
* **Field** — prices, fees, reserves, liquidity generate a directed opportunity field over those paths
* **Motion** — agents exploit the directed opportunity field; those actions are transactions
* **Backreaction** — transactions change reserves and liquidity, changing the field that caused them
* **Dynamics** — the repeated loop generates endogenous market behavior



A road stays put when a car crosses it. A liquidity network does not: a swap is not just passing through a pipe — it is reshaping the pipe. Using the graph changes the state of the graph (reserves, prices, ticks, edge weights); only adding or removing pools changes its topology.

> state → incentive → transaction → new state → new incentive

***

### One Conserved Root. Many Local Price Surfaces.

The same fungible NUT trades on Uniswap V2, V3, Aerodrome, and Balancer — none speaks the other's language, yet fractions of the one unit live inside all of them. Each venue produces an executable exchange rate from its own reserves, liquidity, fees, and curve.



**There is no canonical on-chain price of NUT** — only local executable prices, coupled by arbitrage, which exists precisely because those prices are commensurable.



The spread is not a flaw; it is the honest observable of one root living in many jobs.

> Price is not stored in NUT. Price is produced by the state of the market observing NUT.



### Arbitrage, in Plain Words

The same NUT trades in many markets at once — Uniswap V2, V3, Aerodrome, Balancer, bonding curves. Every market has its own price, so sometimes the same NUT is cheaper in one place and pricier in another.

**Arbitrage is buying it where it is cheap and instantly selling it where it is dear**, pocketing the difference. That gap-closing is not cheating or a bug — it is the ecosystem keeping itself honest. Bots race to find these gaps, which pulls every venue's price back into line. Multi-venue fragmentation creates the possibility of discrepancies; arbitrage economically couples those venues back into line. Because NUT is one conserved unit spread across many venues, its price surfaces are coupled by a shared root.



### The Reflexivity Loop

> scarce root → multiple venues → child minting → index wrapping → price gaps → arbitrage → root reprices → repeat

The system is **reflexive** — child assets derive value from NUT, and their activity feeds back to NUT's price. Contracts execute deterministically and agents choose actions under those rules — the graph does not vote. NUT itself just shows up.



### The Full State

The allocation vector x\_t is fundamental, but it is not the whole ecosystem. The full state is a tuple of observables:

<table><thead><tr><th width="241">Component</th><th>Meaning</th></tr></thead><tbody><tr><td>x_t — NUT allocation</td><td>The conserved simplex share of NUT itself</td></tr><tr><td>R_t — reserves</td><td>Counter-asset and collateral reserves per venue</td></tr><tr><td>L_t — liquidity</td><td>Liquidity positions, range, and depth</td></tr><tr><td>Q_t — derived states</td><td>Child-token and index states built on NUT</td></tr><tr><td>Θ_t — parameters</td><td>Fees, curve parameters, weights, mechanism settings</td></tr><tr><td>M_t — memory</td><td>History-dependent observables such as TWAP</td></tr><tr><td>E_t — external environment</td><td>wETH, cbBTC, AERO, gas, block conditions, broader liquidity</td></tr></tbody></table>

Valid actions are **lawful state transformations**: swaps, curve mints, redemptions, joins, exits, and liquidity moves are different transition operators. Every valid transition changes state while preserving the conservation identity ∑x(t+1) = ∑x(t) = 1.

A pNUT claim is not NUT counted twice; child-token supply is not additional NUT. Derived claims live in the broader state vector, not the conserved sum. **One conserved root — everything interesting happens around that equality.**



#### State versus History

Two histories can land on the same NUT allocation while leaving different TWAP observations, LP configurations, or agent positions behind. That is why the allocation map is fundamental but insufficient — and what gives "TWAP is memory" a real function: the machine can carry history beyond the current allocation vector.



### Macro Observables — Proposed Metrics

NUT is observable at several scales: assignments and ticks (micro); pools, bonding curves, index balances (meso); effective float, concentration, price dispersion (macro).

<table><thead><tr><th width="196">Observable</th><th>What it measures</th></tr></thead><tbody><tr><td>HHI</td><td>Concentration of allocation</td></tr><tr><td>Entropy</td><td>Dispersion of allocation</td></tr><tr><td>Effective float</td><td>Accessible NUT, F ≤ 1</td></tr><tr><td>Price dispersion</td><td>Spread across venues</td></tr><tr><td>Arbitrage half-life</td><td>How fast gaps close</td></tr><tr><td>Collateral-lock ratio</td><td>NUT committed as collateral</td></tr><tr><td>Routing centrality</td><td>How much flow passes each venue</td></tr><tr><td>NUT velocity</td><td>How often the same NUT moves</td></tr></tbody></table>

Δ S\_NUT = 0 does not imply Δ economic complexity = 0.

A monetary system does not need an expanding base asset to support an expanding economy — **economic expansion can occur through increasingly sophisticated structures built around that base**.

**The experiment:** can more markets, routes, claims, liquidity configurations, derived assets, and economic relationships expand economic state and functionality while S\_NUT = 1 remains invariant?



***

### Open Questions — Research Lenses, Not Claims

<table><thead><tr><th width="292">Lens</th><th>Research question</th></tr></thead><tbody><tr><td>Spectral modes &#x26; eigenmodes</td><td>Are there persistent modes of system-wide NUT redistribution, or is movement idiosyncratic?</td></tr><tr><td>Koopman operator analysis</td><td>Can observables (reserve ratios, price dispersion, spreads) reveal coherent modes of nonlinear NUT dynamics?</td></tr><tr><td>Stability theory</td><td>After a disturbance, does the ecosystem return toward a bounded region, remain displaced, or transition regimes?</td></tr><tr><td>Fixed points &#x26; no-arbitrage regions</td><td>Does the system repeatedly return to a measurable no-arbitrage region, and how wide is it?</td></tr><tr><td>Limit cycles</td><td>Do repeated NUT flows emerge from internal feedback alone, or from external shocks?</td></tr><tr><td>Bifurcations &#x26; regime transitions</td><td>Are there parameter values at which the machine changes regime?</td></tr><tr><td>Renormalization &#x26; multiscale dynamics</td><td>Which variables remain informative when microscopic detail is coarse-grained away?</td></tr><tr><td>Hypergraph theory</td><td>Does a liquidity hypergraph capture systemic dependencies pairwise routing graphs miss?</td></tr><tr><td>Recursive structural analysis</td><td>Which deployed cycles, if any, repeatedly map reserve → claim → market → reserve in a structurally equivalent way?</td></tr><tr><td>Prime-factor state encoding</td><td>Can canonical arithmetic encoding simplify proofs about restricted classes of NUT state transitions?</td></tr><tr><td>FRACTRAN state machines</td><td>Can restricted NUT transition systems be represented as arithmetic programs while preserving conservation?</td></tr><tr><td>Compositional algebra</td><td>Which classes of NUT transformations commute, which are path-dependent, and which algebraic structures describe them?</td></tr><tr><td>State estimation</td><td>What is the smallest sufficient set of on-chain observables needed to reconstruct the economically relevant state?</td></tr><tr><td>On-chain economic genealogy</td><td>Can the ancestry of derived claims be formally tracked through collateral, reserve, index, and liquidity relationships?</td></tr><tr><td>Propagation &#x26; memory</td><td>How do shocks propagate across venues, and what are the delays in their transmission?</td></tr></tbody></table>

### Doctrine Close

> One root. Many markets. Many states. One conserved whole.
>
> The doctrine is conservation. The machine is liquidity. The frontier is dynamics.



> ⚠️ **Experimental Memefi.** NUT is an experimental cryptoeconomic liquidity topology — an unregulated experimental asset and a documented Network Utility Token within the BASED NUT ecosystem. Not investment advice; no guarantee of profit or value retention. Use at your own risk.
