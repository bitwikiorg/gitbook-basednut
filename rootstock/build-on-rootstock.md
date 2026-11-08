# Build on ROOTSTOCK

## Build on ROOTSTOCK

ROOTSTOCK separates **market mathematics, shared accounting, lifecycle extensions, and interaction workflows** so builders can change the part of the AMM they actually need without rebuilding the rest of the exchange.

{% hint style="success" %}
**Choose the narrowest extension surface that solves the problem.**

Change the market mathematics with a **Pool**. Extend an existing Pool with a **Hook**. Create a different interaction or execution path with a **Router**.
{% endhint %}

***

### Choose what to build

| You need to...                               | Build         | Why                                                                               |
| -------------------------------------------- | ------------- | --------------------------------------------------------------------------------- |
| Create a new invariant or pricing model      | Custom Pool   | The Pool owns market-specific mathematics                                         |
| Create a standard weighted market            | Weighted Pool | Reuse established weighted mathematics and configuration                          |
| Add dynamic behavior around an existing Pool | Hook          | Extend supported lifecycle points without replacing the underlying Pool math      |
| Create a new transaction workflow            | Custom Router | Compose Vault operations and settlement into a different user or integration flow |
| Deploy a pool family consistently            | Factory       | Standardize deployment, registration, versioning, and provenance                  |

The distinction is important.

```
Pool
└── What are the rules of this market?

Hook
└── What additional behavior happens around an operation?

Router
└── How should a user or application execute a workflow?

Vault
└── How are shared accounting and settlement enforced?

Factory
└── How is a known implementation deployed and identified?
```

{% hint style="info" %}
A **Factory** is a deployment and provenance mechanism, not a new market primitive.

In the inherited v3 architecture, factory deployment is the recommended pattern for creating known pool families, but Vault registration is a separate protocol operation. Exact ROOTSTOCK-supported deployment paths are documented in Factories & Deployment.
{% endhint %}

***

### Keep the boundaries intact

ROOTSTOCK is modular because each layer has a different responsibility.

A Custom Pool should not need to rebuild token custody or settlement. A Router should not redefine the market invariant. A Hook can extend configured operations, but it does not replace the Vault's accounting guarantees.

```
interaction
    ↓
Router

accounting + settlement
    ↓
Vault

market mathematics
    ↓
Pool

optional lifecycle behavior
    ↓
Hook
```

Keeping those boundaries intact makes extensions easier to understand, integrate, test, and audit.

See Architecture for the complete execution model.

***

### Before writing contracts

Define the system before implementing it.

#### 1. Economic objective

What behavior are you trying to create?

Examples include:

* a new pricing curve;
* a particular portfolio weighting;
* dynamic fees;
* execution constraints;
* a specialized liquidity workflow.

#### 2. State

What state exists, where is it stored, and what can change it?

Separate:

* immutable configuration;
* mutable parameters;
* external inputs;
* role-controlled state.

#### 3. Invariants and accounting rules

What properties must always remain true?

For a custom AMM, this includes the mathematical invariant and the relationships required for safe swaps and liquidity operations.

For Routers and Hooks, it includes the assumptions made about Vault state and settlement.

#### 4. Trust model

Identify every trusted dependency.

This can include:

* permissioned roles;
* Hooks;
* rate providers;
* oracles;
* external contracts;
* administrative controls.

#### 5. Failure behavior

Define what should happen when a dependency:

* reverts;
* returns invalid data;
* becomes unavailable;
* reaches an unexpected state.

#### 6. Integration surface

Decide which existing ROOTSTOCK interfaces should continue to work.

A novel extension is much easier to integrate when standard Routers, Vault operations, indexers, and other infrastructure can still reason about it.

***

### If you are writing Pool mathematics

A mathematical equation is not yet production AMM code.

Pool math must remain safe under the protocol's fixed-point arithmetic and rounding rules.

A Custom Pool needs explicit definitions for:

* valid input domains;
* minimum and maximum parameters;
* rounding direction;
* precision loss;
* overflow and underflow behavior;
* invariant-ratio bounds;
* swap-fee bounds;
* behavior near extreme balances;
* interaction with supported liquidity operations.

{% hint style="warning" %}
A mathematically correct continuous formula can still be unsafe when implemented with finite-precision integer arithmetic.
{% endhint %}

See Rounding & Invariant Approximation.

***

### Test the properties, not only the examples

A production extension should be tested at several levels.

| Test                           | Purpose                                                                                  |
| ------------------------------ | ---------------------------------------------------------------------------------------- |
| **Unit tests**                 | Verify expected behavior for known cases                                                 |
| **Boundary tests**             | Exercise zero, small, large, and limiting values                                         |
| **Invariant / property tests** | Check properties that must remain true across many states                                |
| **Fuzz tests**                 | Explore valid parameter and state spaces automatically                                   |
| **Rounding tests**             | Verify conservative behavior under fixed-point approximation                             |
| **Adversarial tests**          | Exercise Hooks, callbacks, reentrancy boundaries, permissions, and external dependencies |
| **Integration tests**          | Verify behavior against the actual Vault, Router, Pool, and deployment configuration     |
| **Gas profiling**              | Measure the cost of common execution paths                                               |

Novel economic behavior or new trust assumptions should receive independent security review before substantial value depends on them.

***

### Deployment is part of the design

A contract is not fully described by its source code.

Its deployed behavior also depends on:

* constructor parameters;
* factory version;
* Vault registration;
* token configuration;
* permissions;
* attached Hooks;
* mutable roles;
* initialization;
* network and address;
* deployed bytecode.

Factories help make repeated deployments identifiable and reproducible, but the canonical deployment record remains the source of truth for what ROOTSTOCK actually supports.

{% hint style="warning" %}
**Do not describe a contract as deployed ROOTSTOCK infrastructure until its address and deployment provenance have been verified against the canonical ROOTSTOCK deployment artifacts.**
{% endhint %}

***

### Start building

| Guide                  | Use it when...                                              |
| ---------------------- | ----------------------------------------------------------- |
| Build a Custom Pool    | You need new AMM mathematics                                |
| Build a Weighted Pool  | Weighted math already fits the market                       |
| Build a Hook           | You want to extend an existing Pool                         |
| Build a Custom Router  | You need a new execution workflow                           |
| Factories & Deployment | You are ready to create, register, and identify deployments |
