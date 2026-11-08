# Token Compatibility

## Token Compatibility

Token compatibility is a protocol-level safety constraint. ROOTSTOCK's inherited Vault accounting expects ERC-20 behavior that can be reconciled deterministically with recorded balances and transfer amounts.

### Standard tokens

A conventional fixed-balance ERC-20 is the baseline compatible asset type. Token decimals can differ; the Vault normalizes them internally for pool math.

### Rate-bearing tokens

Tokens such as wrapper shares can be configured with a rate provider where the deployment supports that model. The token itself remains transferred in raw units while pool math can use rate-adjusted live balances.

See Rate Providers.

### Problematic behavior

The upstream v3 Vault explicitly treats unusual token behaviors as unsafe unless normalized through a supported wrapper/model. Important categories include:

#### Rebasing balances

If balances change without transfers, internal accounting can diverge from token state or make ownership semantics ambiguous.

#### Double-entry-point / proxy token behavior

Two token addresses representing the same underlying balance can create accounting and asset-identification problems.

#### Fee-on-transfer / deflationary transfers

If the recipient receives less than the amount nominally transferred, settlement based on requested amounts can become incorrect unless the flow explicitly measures and supports that behavior.

#### Callback/reentrant token behavior

Tokens invoking arbitrary external control flow during transfer expand the reentrancy surface.

#### Blacklist/freeze mechanics

An issuer can block Vault/Router transfers, turning an otherwise valid exit or settlement into a revert.

### Compatibility is not asset quality

A token can be technically compatible and economically unsafe. Smart-contract solvency, custody, oracle integrity, issuer control, and market liquidity are separate risk dimensions.

### Listing/integration checklist

Before supporting a token:

1. inspect implementation/proxy behavior;
2. test `transfer`/`transferFrom` accounting;
3. confirm decimals within protocol bounds;
4. identify rebase/fee/callback/freeze behavior;
5. determine whether a rate provider/wrapper is required;
6. fuzz swaps and liquidity settlement using the real token on a fork;
7. document external trust assumptions.
