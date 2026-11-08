# Errors

ROOTSTOCK's inherited v3 contract surface uses Solidity custom errors to reject invalid state, unsafe configuration, failed settlement, unsupported operations, and authorization violations.

For developers, the stable debugging unit is the **4-byte revert selector plus the ABI of the contract version that reverted**—not a human-readable message copied from a documentation page.

***

### Why selectors matter

A custom error is ABI-encoded just like a function call. The first four bytes identify the error signature; any arguments follow in ABI encoding.

A production client should therefore decode a revert against:

```
chain
  + reverting contract address
  + deployment/version
  + matching ABI
  → error selector + arguments
```

If the ABI version is wrong, the same raw revert can be misclassified or remain undecodable.

***

### Core error families

The inherited Vault/Router/Pool system contains errors around:

| Family           | Examples of what can fail                                                    |
| ---------------- | ---------------------------------------------------------------------------- |
| settlement       | non-zero deltas, insufficient settlement, locked/unlocked state              |
| Pool lifecycle   | duplicate registration, not registered, not initialized, already initialized |
| tokens           | invalid count/order/configuration, scaling/rate incompatibility              |
| swaps            | amounts below minimums, max-in/min-out violations, invalid swap state        |
| liquidity        | unsupported kind, invariant-ratio bounds, RPT amount limits                  |
| Hooks            | before/after callback failure, invalid Hook configuration                    |
| fees             | invalid fee bounds, aggregate fee accounting, protocol/creator limits        |
| authorization    | sender not allowed, invalid admin operation                                  |
| pause/recovery   | Pool/Vault pause state, recovery-mode misuse                                 |
| queries          | disabled queries, spoofed quote results                                      |
| ERC-4626 buffers | initialization, asset mismatch, wrap size, buffer balance/state              |
| Routers          | invalid path/amount combinations, unsupported operations, deadline failures  |

This taxonomy is for navigation. The exact error catalog must be generated from the actual ROOTSTOCK build.

***

### Debugging order

{% stepper %}
{% step %}
#### 1. Locate the reverting contract

Use transaction trace data. Do not assume the top-level Router is the layer that produced the error.
{% endstep %}

{% step %}
#### 2. Select the exact ABI

Resolve the contract address through the deployment/version map and load the ABI from the corresponding build.
{% endstep %}

{% step %}
#### 3. Decode selector and arguments

Decode the revert data. Preserve raw revert bytes in logs so decoding can be improved later.
{% endstep %}

{% step %}
#### 4. Classify the responsible layer

Router, Vault, Pool, Hook, token, Authorizer, or an external dependency may each produce different failure classes.
{% endstep %}

{% step %}
#### 5. Reproduce against the same state

When possible, re-run the matching query/simulation at the same block/state and compare inputs.
{% endstep %}
{% endstepper %}

***

### Hook failures deserve special treatment

The inherited Vault exposes distinct errors for failed before/after Hook callbacks. A callback failure tells you **where** execution failed, but not necessarily **why** the Hook rejected the operation.

Inspect the Hook's own revert data and configuration as well as the Vault-level wrapper error.

***

### Generated catalog

Upstream Balancer v3 generates its error documentation from Solidity source and also produces a selector-sorted index. ROOTSTOCK should follow the same pattern.

A machine-readable ROOTSTOCK error artifact should include at least:

```
contract_or_interface
error_name
signature
selector
arguments
source_path
source_commit_or_build
protocol_version
```

Generate it during the contracts build or release process. Do not manually maintain selectors in prose.

{% hint style="warning" %}
Do not copy Balancer's current selector catalog and label it ROOTSTOCK. Even a small fork change can add, remove, or relocate errors. Generate against the build that produced the deployed bytecode.
{% endhint %}

***

### Selector collisions and duplicate locations

The same custom-error signature can legitimately appear in more than one source location and therefore share a selector. A selector index should preserve all known source locations instead of assuming selector → one contract.

The reverting address and deployment version disambiguate which ABI/source context applies.

***

### Public documentation vs generated artifact

This page explains **how to reason about failures**. The generated error catalog should be the exhaustive machine/reference layer.

That separation keeps human documentation readable while still giving SDKs, explorers, and support tooling a complete selector database.
