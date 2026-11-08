# Security Model

## Security Model

ROOTSTOCK's central security design is **separation of responsibilities plus atomic settlement**. Pools do not independently custody and settle every token movement; the Vault maintains the shared accounting context and requires all temporary credits/debts to resolve before completion.

### Core invariants

A secure deployment should preserve at least these properties:

1. **Settlement completeness** — an unlocked Vault context cannot finish with unresolved token deltas.
2. **Pool-share fairness** — liquidity entry/exit cannot mint or redeem more value than permitted by the pool state and rounding rules.
3. **Pool-favoring rounding** — integer approximation must not systematically give an external caller value beyond the exact mathematical result.
4. **Authorization integrity** — privileged configuration changes require the intended role.
5. **Token-accounting integrity** — Vault assumptions about transferred amounts match supported token behavior.
6. **Recovery availability** — emergency mechanisms cannot become a permanent custody lock solely because a privileged actor pauses the system.

### What the Vault does protect

Centralized accounting reduces duplicated implementation risk around:

* balance tracking;
* token scaling;
* settlement;
* common liquidity mechanics;
* pool-share bookkeeping;
* pause/recovery plumbing;
* fee accounting interfaces.

This gives custom pools a smaller surface to implement.

### What the Vault cannot prove

The Vault does not prove that:

* a custom invariant is economically sensible;
* a hook is benign;
* a rate provider reports a sound value;
* an ERC-20 behaves conventionally;
* an asset is solvent or maintains a peg;
* an oracle cannot be manipulated;
* an administrator will never exercise a permitted action;
* a Router or frontend selected the best trade.

Those risks live at other boundaries.

### Atomicity

A transaction can compose multiple internal operations while remaining all-or-nothing. This reduces intermediate transfer requirements but increases the importance of correctly accounting for every transient credit/debt and callback.

Atomicity prevents a partial onchain completion; it does **not** make a bad atomic trade economically safe.

### Immutability and upgradeability

Assess immutability contract by contract. An immutable Pool can still rely on mutable fee settings, hooks, rates, Routers, or permission systems. Conversely, a configurable contract can have tightly bounded roles.

Security documentation must therefore describe actual control surfaces rather than use “immutable” as a blanket protocol adjective.

### Fork-specific review

ROOTSTOCK should maintain a diff-based security process against its Balancer v3 upstream:

```
upstream audited code
      + ROOTSTOCK modifications
      + deployment configuration
      + new hooks/pools/routers
      = ROOTSTOCK review scope
```

The security scope is the whole expression, not only the unchanged upstream code.
