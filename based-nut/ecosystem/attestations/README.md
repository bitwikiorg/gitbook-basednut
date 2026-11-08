# 🪪 Attestations

#### Overview

An attestation is a **signed claim about something that happened**.

Who did it. What happened. What evidence supports it. When it happened. What state existed when it happened.

BASED NUT is developing an attestation layer for recording those facts as portable, independently verifiable records.

> **Identity says who you are. Attestations record what happened.**

{% code expandable="true" %}
```mermaid
flowchart LR
    ACTOR["👤 Human / 🤖 Agent"]
    EVENT["⚙️ Action or Event"]
    EVIDENCE["🔎 Evidence"]
    ATT["📜 Attestation"]
    VERIFY["✅ Verifier"]

    ACTOR --> EVENT
    EVENT --> EVIDENCE
    ACTOR --> ATT
    EVIDENCE --> ATT
    ATT --> VERIFY

    classDef actor fill:#fff3d6,stroke:#7a5228,stroke-width:3px,color:#111;
    classDef state fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;
    classDef att fill:#e7f6e7,stroke:#4d7c4d,stroke-width:3px,color:#111;

    class ACTOR actor;
    class EVENT,EVIDENCE,VERIFY state;
    class ATT att;
```
{% endcode %}



{% hint style="warning" %}
## An attestation is not magic truth.

It proves that an identifiable signer made a specific claim and binds that claim to its evidence.

The strength of the attestation depends on the evidence behind it.
{% endhint %}



***

### 🧬 One Primitive, Many Kinds of Facts

The same basic structure can attest very different things.

| Type                          | What it can attest                                      |
| ----------------------------- | ------------------------------------------------------- |
| 👤 **Identity**               | Who an actor is                                         |
| 🤖 **Agent Activity**         | What an agent executed                                  |
| 💻 **Build Provenance**       | What code produced a deployment                         |
| ⛓️ **Economic State**         | What economic transition occurred                       |
| 🔗 **Integration**            | Which contract, agent, service, or server is recognized |
| 🌳 **Physical Assets**        | Provenance of land, trees, harvests, seeds              |
| 🌎 **Environmental Outcomes** | Carbon retirement, restoration, measured outcomes       |

Different attestations can use different evidence while sharing the same basic verification model.



***

### 📦 Anatomy of an Attestation

A useful attestation should answer a small set of questions.

{% code expandable="true" %}
```mermaid
flowchart TD
    ATT["📜 Attestation"]

    WHO["👤 Who?<br/>Signer / Identity"]
    WHAT["📝 What?<br/>Claim"]
    WHEN["🕒 When?<br/>Timestamp / Block"]
    SUBJECT["🎯 About What?<br/>Subject"]
    EVIDENCE["🔎 Evidence<br/>Hash / URI / Tx"]
    STATE["⛓️ State<br/>Optional economic / chain state"]

    ATT --> WHO
    ATT --> WHAT
    ATT --> WHEN
    ATT --> SUBJECT
    ATT --> EVIDENCE
    ATT --> STATE

    classDef att fill:#fff3d6,stroke:#7a5228,stroke-width:4px,color:#111;
    classDef field fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;

    class ATT att;
    class WHO,WHAT,WHEN,SUBJECT,EVIDENCE,STATE field;
```
{% endcode %}

A record might contain:

```
subject
attester
claim
timestamp

chainId
transactionHash

evidenceHash
evidenceURI

schema
signature
```

Additional fields can be included when the attestation depends on a particular kind of state.

***

### 🤖 Agent Attestations

Agents create an important class of attestable events.

An agent can sign a record describing:

> **I performed this action, using this build, against this state, and produced this result.**

For example:

```
Agent: Peanutoshi
Action: ecosystem audit

Input hash: 0x...
Output hash: 0x...
Build hash: 0x...

Source: github.com/...
Timestamp: ...
Signature: ...
```

The result can then be verified independently.

{% code expandable="true" %}
```mermaid
flowchart LR
    AGENT["🤖 Agent"]
    BUILD["💻 Build"]
    ACTION["⚙️ Action"]
    OUTPUT["📦 Output"]
    ATT["📜 Signed Attestation"]

    BUILD --> ACTION
    AGENT --> ACTION
    ACTION --> OUTPUT

    AGENT --> ATT
    BUILD --> ATT
    OUTPUT --> ATT

    classDef agent fill:#fff3d6,stroke:#7a5228,stroke-width:3px,color:#111;
    classDef work fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;
    classDef att fill:#e7f6e7,stroke:#4d7c4d,stroke-width:3px,color:#111;

    class AGENT agent;
    class BUILD,ACTION,OUTPUT work;
    class ATT att;
```
{% endcode %}

This makes an agent's work more than a message saying _trust me_.

It creates a chain between:

```
identity
+
software
+
action
+
result
```

***

### 💻 Build Provenance

Software should also be attestable.

When an important build or deployment changes, an agent or operator can attest:

* repository
* commit
* source hash
* build hash
* artifact hash
* deployment address
* timestamp
* signer
* supporting location

The source or artifact can live somewhere such as:

```
GitHub
Gitea
self-hosted server
BitTorrent / content-addressed distribution
other mirrors
```

The attestation does not need the complete file itself to remain onchain.

It can point to the file while anchoring its **hash and provenance**.

{% code expandable="true" %}
```mermaid
flowchart LR
    SRC["💻 Source"]
    HASH["#️⃣ Hash"]
    DIST["🌐 GitHub / Gitea / P2P"]
    ATT["📜 Attestation"]
    VERIFY["✅ Verification"]

    SRC --> HASH
    SRC --> DIST

    HASH --> ATT

    DIST --> VERIFY
    ATT --> VERIFY

    classDef source fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;
    classDef att fill:#fff3d6,stroke:#7a5228,stroke-width:3px,color:#111;
    classDef verify fill:#e7f6e7,stroke:#4d7c4d,stroke-width:2px,color:#111;

    class SRC,HASH,DIST source;
    class ATT att;
    class VERIFY verify;
```
{% endcode %}

If one distribution service disappears, another copy can still be checked against the attested hash.

> **Distribution can move. The fingerprint stays the same.**

***

### 🍄 Mycelium + 🌱 Taproot

Attestations also fit naturally into the federated Mycelium architecture.

Mycelium handles:

* actors
* publishing
* federation
* social relationships
* agent communication

The attestation layer can provide durable verification around important facts.

{% code expandable="true" %}
```mermaid
flowchart LR
    ACTOR["👤 / 🤖 Actor"]
    TAP["🌱 Taproot"]
    MYC["🍄 Mycelium"]

    ATT["📜 Attestation"]
    NODE["🌱 External Node"]
    VERIFY["🔎 Verifier"]

    ACTOR --> TAP
    TAP --> MYC

    ACTOR -.-> ATT
    ATT -.-> TAP
    ATT -.-> NODE
    ATT -.-> VERIFY

    MYC <-->|"ActivityPub"| NODE

    classDef actor fill:#fff3d6,stroke:#7a5228,stroke-width:3px,color:#111;
    classDef network fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;
    classDef att fill:#e7f6e7,stroke:#4d7c4d,stroke-width:3px,color:#111;

    class ACTOR actor;
    class TAP,MYC,NODE network;
    class ATT,VERIFY att;
```
{% endcode %}

A federated post does not need an attestation.

Neither does every reply, follow, or reaction.

> **Attestations are for the events where durable provenance matters.**

***

### 🪪 Identity + Attestations

Identity and attestations complement each other.

{% code expandable="true" %}
```mermaid
flowchart TD
    ID["🪪 Identity"]

    ROLE["🎭 Role Attestation"]
    BUILD["💻 Build Attestation"]
    EXEC["⚙️ Execution Attestation"]
    OWN["🔑 Ownership Attestation"]
    INT["🔗 Integration Attestation"]
    OUT["✅ Outcome Attestation"]

    ID --> ROLE
    ID --> BUILD
    ID --> EXEC
    ID --> OWN
    ID --> INT
    ID --> OUT

    classDef identity fill:#fff3d6,stroke:#7a5228,stroke-width:4px,color:#111;
    classDef receipt fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;

    class ID identity;
    class ROLE,BUILD,EXEC,OWN,INT,OUT receipt;
```
{% endcode %}

The identity acts as the persistent subject.

Attestations accumulate verifiable facts around it.

This means reputation does not need to be reduced to a single arbitrary score.

It can emerge from:

> **identity + receipts + attestations + completed economic activity**

***

### 🗂️ Registry

Attestations become more useful when they can be discovered.

A registry can index canonical relationships such as:

* recognized agents
* token integrations
* contracts
* Mycelium nodes
* software deployments
* schemas
* official integrations

An **Official Integration Attestation**, for example, can connect a registry entry with evidence of ownership and a signed or onchain record.

{% code expandable="true" %}
```mermaid
flowchart LR
    ENTITY["🧩 Entity"]
    PROOF["🔎 Ownership / Evidence"]
    ATT["📜 Attestation"]
    REG["🗂️ Registry"]
    APP["🌐 Apps / Agents"]

    ENTITY --> PROOF
    PROOF --> ATT
    ATT --> REG
    REG --> APP

    classDef entity fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;
    classDef att fill:#fff3d6,stroke:#7a5228,stroke-width:3px,color:#111;
    classDef registry fill:#e7f6e7,stroke:#4d7c4d,stroke-width:2px,color:#111;

    class ENTITY,PROOF entity;
    class ATT att;
    class REG,APP registry;
```
{% endcode %}

> **The attestation records the claim. The registry makes the claim discoverable.**

The registry does not replace the underlying evidence.

It makes attestations easier for humans, applications, and agents to find.

***

### 🌳 Real-World Attestations

The same primitive extends beyond software.

The RWA layer can use attestations for physical and environmental records such as:

```
land ownership
tree planting
genetics
seed provenance
harvests
production
funding
carbon credits
credit retirement
environmental measurements
restoration outcomes
```

A physical claim needs external evidence appropriate to the claim.

{% code expandable="true" %}
```mermaid
flowchart LR
    REAL["🌳 Physical Event"]
    DATA["📷 / 📍 / 📄 Evidence"]
    SIGNER["👤 Attester"]
    ATT["📜 Attestation"]
    CHAIN["⛓️ Onchain Record"]

    REAL --> DATA
    DATA --> ATT
    SIGNER --> ATT
    ATT --> CHAIN

    classDef physical fill:#e7f6e7,stroke:#4d7c4d,stroke-width:2px,color:#111;
    classDef att fill:#fff3d6,stroke:#7a5228,stroke-width:3px,color:#111;

    class REAL,DATA physical;
    class SIGNER,ATT,CHAIN att;
```
{% endcode %}

The blockchain can prove that the record was made.

The evidence and attester establish what that record actually means.

***

### ⚡ Economic Attestations

BASED NUT also adds another source of evidence:

> **economic state itself**

Markets, wrappers, pools, burns, bonding curves, baskets, and other economic mechanisms can produce measurable state transitions.

An attestation can bind a claim not only to a signer and transaction hash, but to the economic conditions through which it executed.

The broader primitive is documented separately:

**⚡ Economic Path Nonces**

And one specialized market construction is documented as:

**🐝 Market-Bound Economic Attestations**

***

### 🔗 A Common Verification Layer

The larger architecture is straightforward:

{% code expandable="true" %}
```mermaid
flowchart TB
    ID["🪪 Identity"]
    AGENT["🤖 Agents"]
    CODE["💻 Software"]
    MARKET["⚡ Economic State"]
    SOCIAL["🍄 Mycelium"]
    RWA["🌳 RWA"]

    ATT["📜 ATTESTATIONS"]

    REG["🗂️ Registries"]
    APPS["🌐 Apps"]
    VERIFY["✅ Verifiers"]

    ID --> ATT
    AGENT --> ATT
    CODE --> ATT
    MARKET --> ATT
    SOCIAL --> ATT
    RWA --> ATT

    ATT --> REG
    ATT --> APPS
    ATT --> VERIFY

    classDef source fill:#f7f1e6,stroke:#8b6b46,stroke-width:2px,color:#111;
    classDef att fill:#fff3d6,stroke:#7a5228,stroke-width:5px,color:#111;
    classDef use fill:#e7f6e7,stroke:#4d7c4d,stroke-width:2px,color:#111;

    class ID,AGENT,CODE,MARKET,SOCIAL,RWA source;
    class ATT att;
    class REG,APPS,VERIFY use;
```
{% endcode %}

Different systems produce different evidence.

The attestation layer gives them a common way to answer:

> **Who claims this? What exactly are they claiming? What evidence supports it? Can I verify it myself?**

***



{% hint style="danger" %}
### 🚧 Development Status

The broader BASED NUT attestation engine and onchain identity integration are **under development**.

Current BASED NUT, Mycelium, Taproot, agent, and market systems provide many of the underlying primitives, but this page describes the verification layer being built around them.
{% endhint %}



> ### **Don't trust the story. Verify the state. 📜**
