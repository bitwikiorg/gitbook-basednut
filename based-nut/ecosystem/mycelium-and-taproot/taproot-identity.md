# 🫚 Taproot Identity

**Status: PROPOSED ARCHITECTURE** — Taproot is the identity primitive used by the BASED NUT attestation system. Contract standard and final lifecycle policy remain implementation decisions until deployed.

### Primitive

The central distinction is:

> **An account is not an identity.**

A wallet is a cryptographic controller.

An identity is the persistent subject that wallets, names, attestations, permissions, agents, and applications can reference.

```
               Taproot Identity
                      │
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
     wallets        names      attestations
        │                           │
        ↓                           ↓
 permissions                     history
        │
        ↓
 applications / agents
```

### Taproot, Mycelium, Attestations

The architecture separates three jobs:

```
Taproot      = identity
Mycelium     = network
Attestations = claims and evidence
```

Taproot answers:

> What persistent subject are we talking about?

Mycelium answers:

> How do subjects, servers, agents, and applications connect?

Attestations answer:

> What has been claimed, observed, authorized, completed, or verified about that subject?

### Identity ≠ Wallet

A wallet can control or act for an identity, but the address itself should not be treated as the complete semantic identity.

Why separate them?

* humans may use several accounts;
* agents may rotate execution accounts;
* organizations may use multisigs or modules;
* applications need a stable subject for history;
* attestations should survive interface changes;
* permissions should attach to a subject and an explicit controller relationship.

The exact controller/recovery policy must be defined by the deployed implementation. This page does not assume that transfer, recovery, burning, or reminting is available until those rules are explicitly chosen.

### Identity ≠ Name

Names are human-readable resolvers over identities.

```
alice.nut
    ↓
Taproot identity
    ↓
controllers / records / attestations
```

The identity exists at the protocol layer.

The name makes it legible.

Applications can display a name without using the name itself as the permanent subject of every record.

### Shared Namespace Rule

The planned BASED NUT naming model uses a shared label space across resolver namespaces.

```
alice.nut
alice.root
```

should not represent two independently claimable `alice` labels.

If `alice` is occupied in one BASED NUT namespace, the same label is unavailable in the sibling namespace.

Conceptually:

```
labelHash("alice") → one namespace occupancy record
```

and the selected suffix determines resolver/lifecycle semantics rather than creating a second independent identity named `alice`.

This prevents namespace duplication from fragmenting semantic identity.

### Names Are Not Ownership of the Subject

A name can resolve to an identity, but owning or controlling a name does not prove a real-world fact about the subject.

For example:

```
orchard-7.nut
```

does not prove ownership of Orchard 7.

That requires a separate attestation, legal record, registry reference, or other evidence.

Names answer **where to resolve**.\
Attestations answer **what is claimed**.

### Identity Types

Taproot should be general enough to identify more than humans.

Possible subjects include:

* humans;
* agents;
* organizations;
* servers;
* projects;
* farms;
* parcels;
* contracts;
* pools;
* datasets;
* assets.

Applications can interpret the subject type through explicit records or attestations rather than by changing the underlying identity primitive.

### Attestations About Identity

Identity becomes useful through attributable history.

Examples:

```
Identity A
 ├── controlled by wallet X
 ├── resolves name alice.nut
 ├── operates agent P
 ├── member of organization O
 ├── completed job J
 ├── owns/operates project R
 └── received verification V
```

These are separate claims.

They should not be compressed into one mutable profile field when provenance matters.

See Attestations.

### Economic Nonces

An identity can optionally bind an action or attestation to a market-bound economic nonce.

```
identity
   ↓
payload / action
   ↓
NUT/wNUT state transition
   ↓
economic nonce
   ↓
attestation
```

This links identity, payload, and economic execution.

It proves execution provenance, not the truth of the payload.

### Permissions and Mandates

Identity should be separable from authority.

```
identity
  ↓
permission / mandate
  ↓
controller or agent
  ↓
action
  ↓
receipt / attestation
```

A controller can be authorized to perform a bounded action without becoming the identity itself.

This is important for autonomous agents and organizational accounts.

### Reputation Is Derived

Taproot should not require one universal reputation score.

Reputation can be derived by applications from:

```
identity
+ receipts
+ attestations
+ completed activity
+ counterparties
+ time
```

Different applications can weight the same history differently.

The ledger stores facts and claims. Applications derive judgments.

### RWA Identity

Real-world credit needs stable subjects.

```
farm identity
parcel identity
borrower identity
verifier identity
warehouse identity
buyer identity
carbon project identity
```

Attestations can then reference the same subjects across planting, inspection, inventory, financing, carbon issuance, transfer, retirement, and repayment.

This prevents each document from inventing a new disconnected identifier.

### Design Invariants

1. **Identity is not an account.**
2. **Identity is not a name.**
3. **Names resolve to identities.**
4. **Attestations reference identities.**
5. **Permissions authorize actions for identities.**
6. **Mycelium connects identities and services without redefining identity.**
7. **Reputation is derived from history, not stored as one canonical score.**
8. **Economic nonces are optional execution proofs, not identity itself.**
9. **Namespace labels should not fragment across `.nut` and `.root`.**
10. **Lifecycle behavior must be explicit in the deployed contract rather than inferred from branding.**

### Related

* Attestations
* Market-Bound Economic Nonces
* NUT Credit
* Agricultural Credit
* Carbon Credits

> ⚠️ **Experimental architecture.** Taproot describes the intended identity model; deployed contract semantics are authoritative once a production implementation exists.
