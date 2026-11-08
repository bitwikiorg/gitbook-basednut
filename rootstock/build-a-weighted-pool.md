# Build a Weighted Pool

## Build a Weighted Pool

Build a **Weighted Pool** when the market can be expressed through fixed token weights rather than a new invariant.

Weighted Pools use the standard weighted-product invariant. You choose the assets, weights, fee configuration, permissions, optional Hook, and deployment settings; the existing Pool implementation supplies the market mathematics.

{% hint style="success" %}
**Do not build custom AMM math when Weighted Math already describes the market.**

Use a Custom Pool only when the desired pricing function cannot be represented by fixed weights.
{% endhint %}

***

### Weighted invariant

For token balances (B\_i) and normalized weights (w\_i):

$$
V=\prod_i B_i^{w_i}
$$

with:

$$
\sum_i w_i=1
$$

A two-token `50 / 50` pool belongs to the familiar constant-product family.

Changing the weights changes the market.

```
50 / 50
→ symmetric exposure

80 / 20
→ majority / minority exposure

60 / 20 / 20
→ multi-asset weighted basket
```

Weights affect both:

* the Pool's inventory exposure; and
* how changes in balances move its relative prices.

They are therefore economic parameters, not cosmetic percentages.

***

### Inherited Weighted Pool bounds

The standard Balancer v3 Weighted Pool provides the mathematical baseline inherited by ROOTSTOCK.

| Constraint                      |              Upstream v3 baseline |
| ------------------------------- | --------------------------------: |
| Pool size                       |                        2–8 tokens |
| Minimum normalized weight       |                      1% per token |
| Sum of weights                  |                              100% |
| Weight changes after deployment |                     Not supported |
| Static swap fee                 |                        0.001%–10% |
| Maximum swap in/out ratio       | 30% of the relevant token balance |
| Liquidity invariant ratio       |         0.70×–3.00× per operation |

{% hint style="info" %}
These are **inherited v3 constraints**, not a substitute for the canonical ROOTSTOCK contracts.

The deployed ROOTSTOCK Weighted Pool implementation and factory remain the source of truth for the limits supported by a particular release.
{% endhint %}

The minimum-weight rule also constrains how dominant one asset can become.

For example, under the inherited 1% minimum:

```
2 tokens → maximum dominant weight 99%
3 tokens → maximum dominant weight 98%
4 tokens → maximum dominant weight 97%
```

Every other asset must still satisfy its own minimum weight.

***

### 1. Choose the assets

Start with the tokens that will define the market.

Evaluate:

* ERC-20 behavior;
* decimals;
* transfer behavior;
* token type;
* rate-provider requirements;
* liquidity and external market quality;
* volatility;
* correlation;
* oracle or external-contract dependencies;
* administrative or upgrade risk.

A token can be mathematically compatible with Weighted Math and still be operationally unsuitable for the Pool.

{% hint style="warning" %}
**Token risk becomes Pool risk.**

A weighting does not protect the market from a broken token, compromised rate provider, malicious upgrade, or failed external dependency.
{% endhint %}

See Token Types and Token Compatibility.

***

### 2. Choose the weights

Weights describe how the market allocates exposure across its assets.

Examples:

| Composition         | Interpretation                                |
| ------------------- | --------------------------------------------- |
| `50 / 50`           | Symmetric two-token market                    |
| `80 / 20`           | Majority/minority exposure                    |
| `60 / 20 / 20`      | One dominant asset with two smaller positions |
| `25 / 25 / 25 / 25` | Equal-weight multi-asset basket               |

#### Rooted composition

ROOTSTOCK calls a Weighted Pool **rooted** when one designated root asset has a majority normalized weight.

```
70 / 30
70 / 20 / 10
60 / 20 / 20
```

The underlying mathematical family is still **Weighted**.

```
Weighted Pool
└── composition
    ├── 50 / 50
    ├── equal-weight basket
    ├── rooted
    └── other valid fixed weights
```

{% hint style="info" %}
**Rooted is a composition, not a separate invariant.**

Building a rooted pool does not require custom Pool mathematics.
{% endhint %}

See Rooted Pools.

#### Weights are deployment decisions

In the inherited standard Weighted Pool, normalized weights are fixed when the Pool is deployed.

If the market requires weights that change over time, do not assume a standard Weighted Pool can mutate them. That requires a different Pool design or another explicitly supported mechanism.

***

### 3. Choose the fee configuration

Choose the initial swap fee for the expected market.

Consider:

* asset volatility;
* expected trade size;
* arbitrage frequency;
* external market depth;
* LP economics;
* expected routing flow.

Higher fees can increase revenue per trade but make the Pool less competitive for routing.

Lower fees can attract flow but leave less margin for LPs and less protection against toxic order flow and mathematical precision effects.

#### Static vs dynamic fees

A standard deployment can begin with a static swap fee.

If the deployed ROOTSTOCK Hook system supports dynamic fee computation, a configured Hook can introduce fee behavior that changes with market state or other inputs.

```
Weighted Pool
    +
dynamic-fee Hook
    =
Weighted Math with dynamic fee behavior
```

The Pool remains Weighted. The Hook changes behavior around that Pool.

See Dynamic Fees.

***

### 4. Configure token rates where required

Some assets represent claims whose value relative to an underlying asset changes over time.

Examples can include:

* yield-bearing wrappers;
* staking derivatives;
* other rate-bearing tokenized positions.

Where supported, the Vault's token configuration can associate such an asset with a **rate provider**.

The Pool then operates on the protocol's live, scaled representation rather than implementing its own token-rate accounting.

{% hint style="warning" %}
A rate provider is a **security-critical dependency**.

Incorrect, manipulable, stale, or unexpectedly reverting rate data can affect the economic state seen by the Pool.
{% endhint %}

Do not attach a rate provider merely because one exists. Use one only when the token's accounting model requires it and the provider satisfies the expected security properties.

See Rate Providers.

***

### 5. Configure the market envelope

The Pool contract supplies Weighted Math, but registration determines much of the market around it.

Before deployment, decide:

* tokens and token configuration;
* normalized weights;
* initial swap fee;
* role accounts;
* optional Hook;
* supported liquidity behavior;
* donation behavior, if supported;
* pause and recovery configuration;
* deployment salt and versioning;
* external rate dependencies.

This distinction matters:

```
Weighted Pool implementation
    = standard market mathematics

Pool configuration
    = this particular market
```

Two pools can use identical Weighted Math and still have materially different trust and behavior surfaces because their tokens, permissions, Hooks, rates, and fee configuration differ.

***

### 6. Deploy through the ROOTSTOCK factory

Use the canonical ROOTSTOCK Weighted Pool factory intended for the target network and release.

The deployment should make it possible to identify:

* Pool implementation/version;
* factory;
* token set and ordering;
* normalized weights;
* initial swap fee;
* role accounts;
* Hook configuration;
* liquidity-management configuration;
* rate-provider configuration;
* deployment salt or other provenance data where applicable.

{% hint style="danger" %}
**Do not substitute a Balancer deployment address for a ROOTSTOCK deployment address.**

ROOTSTOCK inherits architecture and code lineage from Balancer, not Balancer's production contract identity.
{% endhint %}

A factory provides useful provenance and repeatability, but the factory address alone does not prove that every market created by it has identical risk.

Tokens, Hooks, rate providers, permissions, and registration configuration still matter.

See Factories & Deployment.

***

### 7. Initialize the Pool

Deployment and registration create the market configuration.

**Initialization** creates its first funded state and initial RPT supply.

The initial balances must be chosen together with the Pool weights.

{% hint style="warning" %}
**Weights alone do not set the starting market price.**

The starting balances and normalized weights together determine the Pool's initial marginal price.
{% endhint %}

For example, an `80 / 20` market should not automatically be initialized with `50 / 50` token quantities merely because the tokens have similar external prices.

The intended starting balances must account for both:

* each token's external price; and
* its normalized Pool weight.

If the initialized Pool price differs materially from the external market, arbitrageurs can trade the Pool toward the external price. The initial liquidity position bears that repricing.

See Weighted Pools for the underlying price behavior.

***

### 8. Validate the deployment

Do not treat a successful transaction as sufficient validation.

Check the deployed state against the intended configuration.

#### Configuration

Verify:

* contract and factory version;
* registered tokens;
* token ordering;
* normalized weights;
* rate providers;
* static swap fee;
* role accounts;
* Hook address and enabled behavior;
* liquidity-management settings;
* initialization state.

#### Market behavior

Test:

* a small exact-in swap;
* a small exact-out swap;
* proportional add liquidity;
* proportional remove liquidity;
* supported unbalanced liquidity paths;
* fee behavior;
* Hook behavior, if configured.

#### Accounting and discovery

Confirm:

* RPT supply;
* Vault balances;
* expected events;
* deployment registry entry;
* indexer discovery;
* quote/simulation support.

The deployed Pool should be understandable both **onchain** and **offchain** before it is treated as production liquidity.

***

### When not to use Weighted Math

Weighted Pools are designed for general fixed-weight markets.

Use another Pool family when the economic assumptions are different.

{% tabs %}
{% tab title="Stable Pool" %}
Use Stable Pool mathematics for strongly correlated assets where concentrated liquidity around a known relative price is important.

Weighted Math does not provide the same near-parity capital efficiency.
{% endtab %}

{% tab title="Custom Pool" %}
Use a Custom Pool when the desired pricing or invariant function cannot be represented by fixed Weighted Math.

Do not distort weights to approximate a fundamentally different market equation.
{% endtab %}

{% tab title="Hook" %}
Use a Hook when the Weighted invariant is already correct but the Pool needs additional behavior around swaps, liquidity operations, initialization, or fee calculation.
{% endtab %}
{% endtabs %}
