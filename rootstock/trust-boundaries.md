# Trust Boundaries

## Trust Boundaries

A trust boundary is a point where ROOTSTOCK relies on code, data, assets, or authority outside the immediately executing component. Mapping these boundaries is more useful than labeling the system simply “trustless” or “trusted.”

### Vault ↔ Pool

The Vault trusts a registered Pool to return market calculations consistent with the required interface and numerical bounds. A malicious or flawed custom invariant can misprice trades or liquidity even if Vault settlement remains internally correct.

### Vault ↔ Hook

Hooks introduce external callback logic into the lifecycle. Risks include reentrancy, denial of service, dynamic fee manipulation, privileged parameter changes, and dependence on external contracts.

Treat the Hook address and capability flags as material pool configuration.

### Vault ↔ Token

The Vault assumes supported token transfer/accounting behavior. Rebasing, double-entry-point, callback-heavy, or unusual transfer semantics can break those assumptions unless explicitly handled or wrapped.

See Token Compatibility.

### Vault/Pool ↔ Rate provider

A rate-aware token can depend on an external provider. A stale, manipulable, or reverting rate can affect normalized balances and therefore market/accounting behavior.

A rate provider is not merely display metadata.

### User ↔ Router

The user gives the Router authority to execute a workflow and often to source tokens. Risks include incorrect calldata, excessive approvals, wrong recipient, unsupported Router versions, and inadequate slippage limits.

### Protocol ↔ Authorizer / roles

Privileged accounts can control only the actions granted to them, but those actions may still be economically significant: pausing, changing fees, changing administrative dependencies, or managing recovery/registry settings.

Document role scope and controller type (multisig, timelock, immutable address, etc.) explicitly.

### Pool ↔ external market

AMMs depend economically on arbitrage connecting pool prices to other venues. External market manipulation or illiquidity can therefore affect pool state even without a smart-contract exploit.

### RPT ↔ external protocol

When RPT is used as collateral or nested liquidity, the external protocol creates a new trust and liquidation boundary. RPT composability should not be read as a safety guarantee for every downstream use.

### Boundary-review checklist

For every external dependency ask:

* Can it move assets?
* Can it change prices or fees?
* Can it block execution?
* Can it be replaced?
* Who controls replacement?
* Can it fail/revert/stale?
* Can a same-block actor manipulate it?
* What is the safe failure mode?
