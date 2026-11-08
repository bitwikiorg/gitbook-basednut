# Audits

## Audits

Audits are evidence about a **specific code version and scope**, not a permanent safety certificate for a protocol name.

### Upstream audits

Balancer v3 has undergone multiple security reviews and formal-verification efforts across its core contracts. Those reports are highly relevant to ROOTSTOCK wherever code is inherited unchanged.

They do not automatically cover:

* ROOTSTOCK code modifications;
* new custom pools or hooks;
* changed permissions;
* deployment-script/configuration errors;
* new Routers;
* new external dependencies;
* integrations or frontend behavior.

### ROOTSTOCK audit matrix

Maintain a table that maps each review to exact source provenance:

| Component         | Commit/tag | Reviewer | Report | Findings status | ROOTSTOCK diff covered? |
| ----------------- | ---------- | -------- | ------ | --------------- | ----------------------- |
| Vault             | _verify_   | _verify_ | _link_ | _status_        | _yes/no_                |
| Routers           | _verify_   | _verify_ | _link_ | _status_        | _yes/no_                |
| Weighted Pool     | _verify_   | _verify_ | _link_ | _status_        | _yes/no_                |
| Custom components | _verify_   | _verify_ | _link_ | _status_        | _yes/no_                |

### Diff-aware auditing

For a fork, security review should start from the exact upstream commit and classify every difference:

```
unchanged audited code
modified audited code
new code
removed code
changed deployment/configuration
```

The second through fifth categories require explicit review reasoning.

### Formal verification and invariants

Where upstream formal properties exist, re-run them against compatible ROOTSTOCK code. Add fork-specific properties for Root Pools, rooted configurations, new hooks, or other novel behavior.

### Publication rule

Do not write “ROOTSTOCK is audited” unless the sentence identifies what was audited and which deployed version it covers. Prefer precise statements such as “Vault build X was reviewed by Y; report Z; ROOTSTOCK patch set A/B was included/excluded.”

### Current pack status

No ROOTSTOCK-specific audit reports were available in the connected source set. This page therefore defines the audit registry structure without asserting reviews that have not been verified.
