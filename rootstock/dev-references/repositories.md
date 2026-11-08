# Repositories

Repositories establish code provenance. They tell developers where implementation, application, build, deployment, and audit material comes from—and which source is authoritative for a particular claim.

ROOTSTOCK inherits significant architecture and tooling from Balancer v3, but upstream repositories are lineage, not ROOTSTOCK deployment identity.

***

### ROOTSTOCK application repository

#### `BASEDNUT/rootstock-monorepo`

**Repository:** `https://github.com/BASEDNUT/rootstock-monorepo`

This is the current public ROOTSTOCK monorepo for the product/application surface. The repository contains:

* `apps/frontend-v3` — ROOTSTOCK web application;
* `packages/lib` — shared frontend/domain logic and network configuration;
* audit reports for inherited v3 core/reCLAMM material;
* Base Sepolia application configuration on the Base Sepolia integration branch;
* the local `@balancer/sdk@6.2.0` Base Sepolia address-map patch.

As of **2026-09-26**, the default branch points to `facab6aa9f42d6a3787ababfcc0d3381172ad96b`. The Base Sepolia integration is present on `nut/brand-pass-b` at `de40322e58be81bf31ad30cbaaa14eac37555ce6`.

{% hint style="warning" %}
The public repository does not contain the complete ROOTSTOCK core Solidity fork/build/deployment source that produced the reported Base Sepolia contract set. Do not infer exact deployed bytecode provenance from the frontend repository alone.
{% endhint %}

***

### Upstream contracts

#### `balancer/balancer-v3-monorepo`

**Repository:** `https://github.com/balancer/balancer-v3-monorepo`

This is the primary upstream source for the inherited v3 contract architecture, including:

* Vault interfaces and implementation;
* Router families;
* Hooks;
* Pools and factories;
* Protocol Fee Controller;
* Contract Registry;
* custom errors and events;
* tests and protocol libraries.

Inherited interface statements in this Developer Reference are pinned to upstream commit:

```
2b9ce4b1b8ad49eafcad8d136f0872ea7c7d5d53
```

Use that pin for reproducibility of the inherited-interface statements in these pages. It is **not** a claim that the ROOTSTOCK Base Sepolia bytecode was built from that exact upstream commit.

***

### Upstream deployment metadata

#### `balancer/balancer-deployments`

**Repository:** `https://github.com/balancer/balancer-deployments`

This repository is useful for understanding Balancer's deployment-task/versioning model and upstream addresses.

Do not copy its addresses into ROOTSTOCK's deployment table. Balancer deployments and ROOTSTOCK deployments are different identities even when they implement compatible interfaces.

***

### Upstream SDK

#### `balancer/b-sdk`

**Repository:** `https://github.com/balancer/b-sdk`

ROOTSTOCK's current application depends on `@balancer/sdk@6.2.0`. The application adds its Base Sepolia (`84532`) deployment map through a local package patch on the active ROOTSTOCK branch.

The upstream SDK remains a dependency; the ROOTSTOCK-specific address patch remains ROOTSTOCK application state.

***

### Source-of-truth hierarchy

For an exact claim, choose the source that owns that fact:

| Claim                                            | Authority                                                     |
| ------------------------------------------------ | ------------------------------------------------------------- |
| What address is supported on a ROOTSTOCK chain?  | ROOTSTOCK deployment manifest / verified integration snapshot |
| What bytecode is deployed there?                 | chain + deployment/build provenance                           |
| What ABI decodes it?                             | generated artifact from matching ROOTSTOCK build              |
| What does the ROOTSTOCK frontend currently call? | pinned ROOTSTOCK application source                           |
| What interface behavior was inherited from v3?   | pinned Balancer v3 contract source                            |
| How did Balancer deploy its own system?          | Balancer deployment repository                                |
| How does the current client builder work?        | pinned SDK source/version + ROOTSTOCK patch                   |

In shorthand:

```
ROOTSTOCK deployed bytecode / provenance
        > ROOTSTOCK pinned source + generated artifacts
        > ROOTSTOCK application wiring
        > Balancer v3 source lineage
        > historical documentation
```

***

### Release discipline

A production-ready protocol release should make the relationship between these repositories explicit by publishing:

* the exact ROOTSTOCK contracts repository/revision;
* build/compiler settings;
* generated ABIs and error catalog;
* deployment task/transaction metadata;
* address manifest by chain;
* application/SDK compatibility version.

That chain of provenance turns “forked from Balancer v3” into a reproducible ROOTSTOCK implementation rather than a documentation assumption.
