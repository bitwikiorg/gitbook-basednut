# ⚖️ NUT Equilibrium

{% hint style="danger" %}
### **WARNING: YOU ARE READING** HYPER ADVANCED NUT RESEARCH

We have exhausted the practical explanations and are now investigating what happens when very smart people are left alone with **1 NUT** for too long. The whitepaper needed more symbols. Advanced theory needed more equations. Apparently neither was enough. Welcome to the part where we give the NUT a research PhD program.
{% endhint %}

NUT trades simultaneously across multiple economic mechanisms: AMMs, bonding curves, index structures, and derived-token markets. Each mechanism produces its own local state and executable price while remaining coupled to the others through the same underlying NUT.



The advanced problem is therefore not finding a single NUT price.



It is describing the **collective state of those markets**, how tightly they remain coupled, and how that state changes under arbitrage, liquidity movement, collateralization, and external shocks.



### Friction-Bounded Equilibrium

NUT markets do not converge toward exact price equality.



For a route $$(r)$$ , trade size $$(q)$$ , and system state $$(\Omega_t)$$, let:

$$
\Pi_r(q,\Omega_t)
$$

denote the net executable profit after all route costs.



The NUT network is inside a **no-arbitrage region** for qq when:

$$
\max_{r\in\mathcal R}\Pi_r(q,\Omega_t)\leq0
$$

where R\mathcal R is the set of executable routes being considered.



This defines equilibrium operationally.



Different venues may retain different local prices while the network remains arbitrage-consistent because the remaining discrepancies are smaller than the friction required to close them.

The boundary depends on:

* trade size
* AMM fees
* transfer taxes
* gas
* slippage
* route depth
* intermediate-asset conversion
* execution risk

NUT equilibrium is therefore better represented as a **state-dependent region** than as a single equilibrium point.



***

### Price Dispersion

The distance between local NUT price surfaces provides one measure of market coupling.

For executable NUT prices&#x20;

$$
p_i(q,t)
$$

normalized into a common numeraire, define the weighted mean log price:

$$
\bar{\ell}(q,t)
=
\sum_i \omega_i \ln p_i(q,t)
$$

and executable price dispersion:

$$
D_p(q,t)
=
\sum_i
\omega_i
\left[
\ln p_i(q,t)-\bar{\ell}(q,t)
\right]^2
$$

with:

$$
\sum_i \omega_i = 1
$$



The weights can represent active depth, executable capacity, or another declared market-weighting rule.



The quantity (q) must remain explicit. Two NUT venues can be tightly coupled for small trades and effectively fragmented for larger trades.



Low DpD\_p indicates tightly aligned executable prices.

High DpD\_p indicates greater fragmentation across the NUT market network.



Price dispersion does not itself identify an arbitrage opportunity; profitability still depends on the available routes and their friction.



***

### Allocation Entropy

Equilibrium also concerns the **distribution of NUT itself**, not only its prices.

Let:

$$
x_i(t)
$$

be the fraction of total NUT residing in economic compartment ii, with:

$$
\sum_i x_i(t)=1
$$



The distribution has an allocation entropy:

$$
H_N(t)
=
-\sum_i x_i(t)\ln x_i(t)
$$



This is Shannon entropy applied to the normalized NUT allocation vector.



It measures dispersion of the conserved NUT across the chosen compartment partition:

* lower entropy corresponds to greater concentration
* higher entropy corresponds to greater dispersion



When the number of compartments nn is fixed, normalized allocation entropy can be written:

$$
h_N(t)
=
\frac{H_N(t)}{\ln n}
$$

so that:

$$
0\leq h_N(t)\leq1
$$



Entropy here is an **allocation statistic**, not thermodynamic entropy.



Its value depends on how the ecosystem is partitioned. Wallet entropy, venue entropy, and functional entropy are different observables because they answer different questions.



The useful dynamic quantity is often the change:

$$
\Delta H_N
=
H_N(t_1)-H_N(t_0)
$$

A market event can therefore be studied not only by how much it moves NUT prices, but by whether it causes NUT itself to become more concentrated or more dispersed across economic functions.



***

### The Observable State

The complete on-chain state is too large to serve directly as a useful stability description.



For equilibrium analysis, define an observable vector:

$$
y_t
=
g(\Omega_t)
$$

containing the NUT properties relevant to the problem.



A useful observable state may include:

$$
y_t
=
\left[
D_p,\,
H_N,\,
F_N,\,
L,\,
C,\,
A
\right]_t
$$

where:

* DpD\_p — executable price dispersion
* HNH\_N — NUT allocation entropy
* FNF\_N — effective NUT float
* LL — executable liquidity or depth
* CC — graph-coupling or routing measures
* AA — active arbitrage opportunity

The definitions of FNF\_N, LL, and CC belong to Structural Liquidity and Liquidity Graphs respectively. Here they become components of the system state used to study equilibrium.

This separates **state measurement** from the underlying mechanism that produces it.



***

### Stability

A NUT equilibrium region is stable when disturbances do not cause the measured system state to move without bound or permanently lose its prior structure.



Several responses are possible:

* **recovery** — observables move back toward their previous region
* **displacement** — the system settles into a different bounded region
* **persistent fragmentation** — price or routing differences remain elevated
* **oscillation** — state repeatedly moves through related configurations
* **instability** — deviations amplify rather than decay

Stability is therefore multidimensional.



Price dispersion can recover while allocation entropy remains permanently changed. Liquidity depth can recover while routing centrality migrates to another venue.

There is no reason to expect every NUT observable to stabilize at the same rate or even in the same direction.



***

### Open-System Dynamics

The live NUT network is not an autonomous dynamical system.



Its evolution depends on both internal state and external inputs:

$$
\Omega_{t+1}
=
F(\Omega_t,u_t)
$$

where utu\_t includes exogenous conditions such as:

* WETH, cbBTC, AERO, and other external asset prices
* Base gas and block conditions
* liquidity entering or leaving external venues
* broader market volatility



This distinction is critical when interpreting NUT behavior.



A recurring NUT pattern generated by internal arbitrage is an **endogenous dynamic**.

A similar pattern driven by repeated ETH or BTC movements is an **exogenous response**.



Any stability, cycle, or regime analysis must distinguish the two.



***

### Shock Response

A **shock** is a discrete event large enough to materially perturb the observable NUT state.



Relevant shocks include:

* large NUT swaps
* substantial liquidity additions or removals
* bonding-curve mint or redemption events
* pNUT joins or exits
* large changes in collateral commitment
* sharp movements in major counter-assets



For observable yiy\_i, define the response to shock ss at t0t\_0:

$$
R_i(\tau\mid s)
=
y_i(t_0+\tau)-y_i(t_0^-)
$$

This produces a response profile across time.



The full response can reveal:

* propagation order
* response magnitude
* delay
* decay rate
* overshoot
* persistent state change



The same shock can be evaluated simultaneously through price dispersion, allocation entropy, effective float, liquidity depth, and routing structure.



***

### Arbitrage Half-Life

The decay of a NUT dislocation provides a direct measure of coupling strength.



For a dispersion measure D(t)D(t) observed immediately after a dislocation at t0t\_0, define arbitrage half-life:

$$
\tau_{1/2}
=
\inf
\left\{
\tau>0:
D(t_0+\tau)
\leq
\frac{D(t_0)}{2}
\right\}
$$

A shorter half-life indicates faster removal of the observed discrepancy.

A longer half-life indicates weaker effective coupling under the measured conditions.

Half-life can be measured at different trade sizes, producing a **coupling profile** rather than one system-wide number.

This matters because shallow markets can appear tightly coupled at small size while remaining fragmented at economically larger sizes.



***

### Local Stability and the Jacobian

Near a sufficiently regular reference region, changes in the observable state can be locally approximated by:

$$
\delta y_{t+1}
\approx
J\,\delta y_t
$$

where JJ is the local Jacobian of the fitted dynamics.



The Jacobian captures how small changes in one NUT observable transmit into others.



Its entries can represent relationships such as:

* how price dispersion responds to loss of executable depth
* how arbitrage opportunity responds to increased fragmentation
* how allocation distribution changes following liquidity movement



For a discrete local model, the eigenvalues of JJ determine the behavior of its local modes.

If:

$$
Jv_i
=
\lambda_i v_i
$$

then viv\_i is a coupled mode of movement and λi\lambda\_i describes its local persistence or amplification.

A locally fitted system with spectral radius:

$$
\rho(J)<1
$$

has decaying linearized disturbances.

This statement applies to the **local fitted model**, not automatically to the live NUT network.



***

### NUT Eigenmodes

An eigenmode is useful only if several NUT variables repeatedly move together in a coherent pattern.



Possible empirical modes include:

* redistribution between liquid and collateralized NUT
* migration between NUT price-discovery venues
* coordinated expansion and contraction of cross-venue spreads
* changes in effective float coupled to allocation concentration
* liquidity migration coupled to slower or faster arbitrage convergence

Spectral analysis asks whether a high-dimensional stream of NUT state changes can be decomposed into a smaller set of persistent modes.



If no stable modes appear in the data, the spectral description has no analytical advantage.



***

### Nonlinear Modes and Koopman Analysis

The NUT network is nonlinear because execution changes reserves, liquidity, routes, and subsequent execution conditions.



The **Koopman operator** provides a possible way to study nonlinear dynamics through the evolution of observables rather than directly linearizing the complete state.



For an observable gg:

$$
\mathcal K g
=
g\circ F
$$

Candidate NUT observables include:

* executable price dispersion
* allocation entropy
* effective float
* collateral-lock ratio
* arbitrage opportunity
* routing concentration

The research value is specific: whether these observables admit coherent modes or predictive structure that is not obvious from transaction-level data.



Koopman analysis remains a research method until such structure is demonstrated.



***

### Oscillation and Limit Cycles

Repeated movement is not sufficient evidence of a limit cycle.

A **limit cycle** requires a self-sustaining periodic orbit of the modeled dynamics.



NUT can exhibit repeated flows generated by:

* arbitrage
* liquidity rebalancing
* bonding-curve interaction
* index rebalancing
* reward mechanisms

These become evidence for an endogenous cycle only after external periodic drivers are controlled for.



The distinction is:

$$
\text{recurring observation}
\neq
\text{endogenous limit cycle}
$$

This prevents externally driven market repetition from being mistaken for an internal property of NUT.



***

### Regimes

A **regime** is a region of NUT state space with a distinct statistical or dynamical structure.

Regimes can be identified from combinations of observables rather than from one variable in isolation.



Relevant dimensions include:

* price dispersion
* allocation entropy
* effective float
* executable depth
* arbitrage half-life
* routing concentration
* collateral commitment
* external volatility

A tightly coupled regime may combine low dispersion with short arbitrage half-life and redundant routing.



A fragmented regime may combine persistent dispersion, reduced route depth, and longer convergence times.

A concentrated regime may exhibit low allocation entropy without necessarily being price-fragmented.



These dimensions are independent enough that regime classification should emerge from measured combinations rather than predefined labels.

### Bifurcations and Regime Transitions

A **bifurcation** is a qualitative change in modeled dynamics caused by crossing a critical parameter value.



For NUT, candidate parameters include:

* active liquidity depth
* fee load
* pool weights
* route redundancy
* collateral allocation
* effective float

A transition qualifies as a bifurcation only when a parameter change produces a demonstrable structural change in the fitted dynamics.



Examples of testable transitions include:

$$
\text{fast convergence}
\rightarrow
\text{persistent fragmentation}
$$

or:

$$
\text{decaying disturbance}
\rightarrow
\text{persistent oscillation}
$$

The threshold and the behavioral change must both be identified empirically.

“Regime change” is the broader observational category; “bifurcation” is the stronger dynamical claim.



***

### Coupling, Concentration and Resilience

The most important combined question is how NUT distribution and market coupling interact.

Allocation entropy measures **where the conserved NUT is distributed**.

Price dispersion and arbitrage half-life measure **how strongly its local markets remain economically coupled**.



Structural liquidity measures **how much executable capacity connects those markets**.

These properties need not move together.



A highly dispersed NUT allocation can still produce weak coupling if liquidity is poorly positioned.

A concentrated allocation can still support strong coupling if the remaining liquidity forms deep, efficient routes.



The resulting research space is therefore relational:

$$
\text{allocation}
\longleftrightarrow
\text{liquidity structure}
\longleftrightarrow
\text{market coupling}
\longleftrightarrow
\text{stability}
$$

The objective is to determine which combinations produce robust NUT market states and which combinations produce fragmentation, slow convergence, or regime transitions.



### Research Program

The equilibrium and stability program measures:

* the friction-bounded no-arbitrage region at different trade sizes
* executable NUT price dispersion
* NUT allocation entropy and its change after shocks
* effective-float changes
* arbitrage half-life
* propagation between NUT venues and derived structures
* lead-lag relationships between markets
* persistent redistribution modes
* endogenous versus externally driven oscillation
* parameter thresholds associated with regime changes
* coupling between allocation, liquidity structure, and convergence

The target is not a claim that NUT has one stable equilibrium.

The target is a map of **which NUT states are economically coherent, how they respond to disturbance, and when the network changes regime**.

### Resources

* Wikipedia — Arbitrage
* Wikipedia — Entropy (information theory)
* Wikipedia — Stability theory
* Wikipedia — Lyapunov stability
* Wikipedia — Eigenvalues and eigenvectors
* Wikipedia — Koopman operator
* Wikipedia — Limit cycle
* Wikipedia — Bifurcation theory
