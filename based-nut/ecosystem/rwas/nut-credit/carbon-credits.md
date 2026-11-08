# 🌎 Carbon Credits

**Status: PROPOSED INTEGRATION** — this page describes how independently issued carbon credits and carbon-related contractual claims can interact with NUT Credit. BASED NUT does not issue carbon credits merely by recording data onchain.

### What a Carbon Credit Is

A carbon credit is an environmental unit issued under a defined standard and registry process.

Under Verra's Verified Carbon Standard, one Verified Carbon Unit (VCU) represents **one metric tonne of CO₂ equivalent reduced or removed** by a project after the applicable validation, monitoring, verification, and program review.

The registry is authoritative for the credit's program status.

```
project activity
    ↓
methodology
    ↓
measurement / monitoring / reporting
    ↓
independent validation + verification
    ↓
registry review
    ↓
issuance
    ↓
transfer
    ↓
retirement
```

An onchain token or attestation that references a carbon project does not independently create the underlying registry credit.

### The Critical Separation

```
physical outcome
≠
measurement
≠
attestation
≠
carbon credit
≠
cash proceeds
```

They are connected, but they are not interchangeable.

| Object            | What it means                                            |
| ----------------- | -------------------------------------------------------- |
| Physical outcome  | Carbon reduced, avoided, or removed in the real world    |
| Measurement / MRV | Evidence describing the outcome                          |
| Attestation       | Attributable statement about evidence or lifecycle state |
| Carbon credit     | Unit issued under an external standard/registry          |
| Carbon forward    | Contractual right related to future credits or proceeds  |
| Cash proceeds     | Money paid by a buyer after a transaction                |

### Carbon Credits Inside NUT Credit

Carbon can enter the NUT Credit architecture through several distinct channels.

#### 1. Credit Revenue

A financed agricultural project may eventually generate issued carbon credits.

```
NUT Credit financing
      ↓
productive practice
      ↓
verified carbon outcome
      ↓
issued carbon credit
      ↓
buyer
      ↓
cash proceeds
      ↓
facility repayment / reinvestment
```

The credit itself is not the loan. Its proceeds can become one repayment source.

#### 2. Carbon Forwards

A borrower may have a contractual right to future carbon-credit proceeds before credits exist.

That is a **carbon forward or receivable**, not an issued carbon credit.

The underwriting question becomes:

> What enforceable right exists to future proceeds, under what methodology, project, verifier, registry, delivery schedule, and buyer agreement?

#### 3. Treasury Acquisition and Retirement

If BASED NUT or another treasury acquires credits through an eligible registry account or counterparty, the lifecycle can be recorded:

```
purchase
  ↓
registry ownership / transfer reference
  ↓
treasury attribution
  ↓
optional retirement
  ↓
retirement reference + beneficiary / purpose
```

The registry record remains authoritative. An onchain record can add public provenance and indexing.

#### 4. Benefactor Capital

A company or benefactor can fund verified environmental outcomes directly or commit capital to productive carbon-removing systems.

This capital can be structured to support:

* orchards;
* agroforestry;
* regenerative agriculture;
* land improvement;
* nurseries;
* restoration;
* irrigation or infrastructure that enables verified practice changes;
* research and pilot programs.

The contractual structure determines whether the payer is purchasing credits, pre-purchasing future credits, funding a project, making a grant, or providing another form of capital. Those should never be collapsed into one label.

### Attestations

The Attestation layer can record attributable evidence around the carbon lifecycle:

* project identity;
* land or site identity;
* methodology reference;
* monitoring period;
* measurement datasets or hashes;
* verifier identity;
* verification report reference;
* registry/project identifier;
* issuance identifier and quantity;
* ownership/status references;
* transfer references;
* retirement references;
* beneficiary or retirement purpose;
* linked agricultural-credit facility.

Attestations improve provenance. They do not substitute for registry issuance or verification.

### Identity

Every carbon record has actors:

```
project
land / site
farmer / operator
verifier
registry
buyer
credit holder
retirement beneficiary
```

Identity gives these actors persistent subjects that attestations can reference.

A wallet is a controller or account. It is not automatically the real-world entity.

### Economic Nonces

A market-bound economic nonce can optionally bind a carbon-related attestation to an observable NUT/wNUT market transition.

This proves that a specific payload was committed through a specific economic event.

It does **not** prove:

* that the carbon was removed;
* that the verifier was correct;
* that a registry credit exists;
* that ownership transferred;
* that a retirement is legally effective.

Those claims still depend on their own evidence and authoritative systems.

### Retirement

Retirement is the terminal use state for many voluntary carbon credits.

For Verra VCUs, issuance and retirement are recorded in the Verra Registry. BASED NUT should therefore treat a retirement attestation as a reference to an authoritative registry event, not as a substitute for retirement.

A useful record can bind:

```
registry
credit / serial reference
quantity
retirement transaction / record
beneficiary
purpose
timestamp
supporting documents
```

### Quality and Due Diligence

A carbon credit is not high quality merely because it exists.

A production integration should evaluate:

* methodology;
* additionality assumptions;
* baseline;
* permanence;
* leakage;
* monitoring quality;
* verifier;
* registry;
* vintage;
* geography;
* project type;
* corresponding-adjustment or claims context where relevant;
* reversal/buffer mechanisms;
* legal ownership;
* buyer restrictions;
* retirement status.

NUT Credit should not infer quality from tokenization.

### BASED NUT Seal

Permissionless attestations can be created by anyone.

A **BASED NUT seal**, if used, should mean only that the record passed a published BASED NUT validation policy. The seal should identify:

* the standard applied;
* required evidence;
* verifier requirements;
* review date;
* reviewer/attester identity;
* revocation or correction policy.

It must not imply that BASED NUT is itself the carbon registry unless that ever becomes legally and operationally true.

### Relationship to the Environmental Balance Sheet

The Environmental Balance Sheet is a comparison ledger: emissions pressure versus disclosed response capital.

It is not a carbon-credit registry and does not create liabilities.

Carbon Credits are the outcome-asset layer that can sit downstream of real mitigation/removal activity.

### References

* Verra — Verified Carbon Units: [https://verra.org/programs/verified-carbon-standard/verified-carbon-units-vcus/](https://verra.org/programs/verified-carbon-standard/verified-carbon-units-vcus/)
* Verra — Verified Carbon Standard: [https://verra.org/programs/verified-carbon-standard/](https://verra.org/programs/verified-carbon-standard/)
* Verra Registry lifecycle: [https://verra.org/program-notice/verra-launches-new-registry-enabling-integrated-and-efficient-user-experience/](https://verra.org/program-notice/verra-launches-new-registry-enabling-integrated-and-efficient-user-experience/)

### Related

* NUT Credit
* Agricultural Credit
* Attestations
* Identity
* Environmental Balance Sheet

> ⚠️ **Experimental Memefi.** This page describes a proposed integration architecture, not an issued carbon program or guarantee of environmental integrity.
