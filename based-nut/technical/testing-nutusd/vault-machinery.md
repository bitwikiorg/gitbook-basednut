# 🔬 Vault Machinery

## 🔬 Research — nutUSD Vault Machinery (Experiment V)

Fifth experiment in the nutUSD research series. Experiment I verified the market boundary; Experiment II recorded the failure modes; Experiment III mapped the seizure branches and oracle-zero states; Experiment IV measured liquidity and rates. This experiment exercises the vault layer the production design wraps around the market: the role and timelock machinery, the inflation-attack surface, and the rate limiter that governs how the vault recognizes gains. Every number is a measured on-chain value.

### Questions

<table><thead><tr><th width="82">#</th><th>Question</th><th>Verdict</th></tr></thead><tbody><tr><td>V1</td><td>Does the role and timelock machinery execute as documented?</td><td>Yes — setCurator → submit → execute proven at the fresh-vault zero-default timelock here; the production 3-day wall, the self-wall, and the full submit → pre-expiry revert → expiry execute cycle in Experiment IX</td></tr><tr><td>V2</td><td>Is the classic inflation attack viable at zero recognition rate?</td><td>No — victim shares equal fair shares exactly; the gift is invisible</td></tr><tr><td>V3</td><td>Is it viable at the maximum recognition rate?</td><td>Not in the immediate and same-block sequences tested — recognized gain is zero at the moment of the victim deposit; the timed sequence (gift, wait, repeated accrual, victim deposit) is unmeasured</td></tr><tr><td>V4</td><td>Is a gift to a never-touched vault recognized?</td><td>No — <code>totalAssets</code> stays zero with 100 USDC sitting in the vault</td></tr><tr><td>V5</td><td>How does the vault recognize a large external gain?</td><td>Rate-limited drip toward the real balance — capped per accrual at the recognized base × maxRate × elapsed, compounding across accruals — measured exactly</td></tr></tbody></table>

### Environment

<table><thead><tr><th width="202">Item</th><th>Value</th></tr></thead><tbody><tr><td>Chain</td><td>Base Sepolia (84532)</td></tr><tr><td>Vault</td><td><code>VaultV2</code> via the canonical factory — three configurations</td></tr><tr><td>Loan asset</td><td>Mock USDC (6 decimals)</td></tr><tr><td>Virtual-share offset</td><td><code>virtualShares</code> = 10¹² on every vault, derived from asset decimals — an accounting offset, distinct from the dead shares held by the burn address</td></tr><tr><td>Attacker / victim</td><td>Two ephemeral wallets; attacker deposits 1 base unit, victim deposits 10 USDC after a 100 USDC gift</td></tr></tbody></table>

| Vault                                                                                                    | Recognition rate    | Purpose                                       |
| -------------------------------------------------------------------------------------------------------- | ------------------- | --------------------------------------------- |
| [`0xB2cf495A…0B537Db`](https://sepolia.basescan.org/address/0xB2cf495A73C6a4e6bddB8dE166F66Ec3B0B537Db)  | 0 — frozen          | Inflation attack against a zero-rate vault    |
| [`0xE023094C…967ACe6`](https://sepolia.basescan.org/address/0xE023094C790a66AF12C5b00074D2daD69667ACe6)  | Maximum — 200%/year | Inflation attack and rate-limiter measurement |
| [`0xbB1D316D…Abc82a11`](https://sepolia.basescan.org/address/0xbB1D316DC28b2b2C733CB210343B6553Abc82a11) | Maximum — empty     | Gift to a vault with no depositors            |

### Roles and timelock

The allocator path was exercised end-to-end on both active vaults: `setCurator` → `submit(bytes)` → `execute(bytes)` → `setIsAllocator` → `setMaxRate`. The timelock on `setIsAllocator` reads zero on a fresh vault — the default is no delay — and the submit → execute dance completed with the delay at its default. The curator role and the allocator flag land exactly as the contract documentation describes; no role bypass was attempted and none was needed to complete the configuration.

### Inflation matrix

The classic first-depositor sequence — seed a microscopic position, gift assets to inflate the share price, let the victim deposit — was executed against all three configurations:

| Vault  | Rate      | Attacker shares          | Victim shares vs fair | Gift recognized at deposit                        |
| ------ | --------- | ------------------------ | --------------------- | ------------------------------------------------- |
| Frozen | 0         | 10¹² (the virtual floor) | Equal — exact         | 0                                                 |
| Active | 200%/year | 10¹²                     | Equal — exact         | 0                                                 |
| Empty  | 200%/year | — (no victim)            | —                     | 0 — `totalAssets` reads zero with 100 USDC inside |

* **Frozen vault** — `totalAssets` reads 10.000001 USDC after both deposits — exactly attacker (1 base unit) + victim (10 USDC); the 100 USDC gift does not exist in share math. The victim's shares equal the fair-share prediction exactly.
* **Maximum-rate vault** — the victim deposit lands with recognized assets still at 10.000001 USDC; the 100 USDC gift sits in the real balance (110.000001 USDC) but recognition is zero at the deposit block. The attack needs the gift recognized _before_ the victim — the rate limiter forbids exactly that, in the immediate sequence.
* **Empty vault** — 100 USDC gifted to a vault with no history: `totalAssets` reads zero. A 1-base-unit deposit opens the share ledger at the virtual floor, raw assets 1 base unit.

The virtual-share shield (10¹²) and the rate limiter compose: the shield blocks the rounding attack on an empty or near-empty vault, and the limiter blocks the recognition-timing attack on an active one. The classic attack is structurally dead in the immediate sequences measured, in both configurations.

### Rate limiter — drip measured

The active vault (real balance 110.000001 USDC, recognized 10.000761 USDC) was left idle 162 seconds, then `accrueInterest()` was called:

| Measure           | Value                                                                               |
| ----------------- | ----------------------------------------------------------------------------------- |
| Recognized before | 10,000,761 — 10.000761 USDC                                                         |
| Elapsed           | 162 s (block timestamps)                                                            |
| Recognition cap   | recognized × maxRate × elapsed per accrual — 200%/year, compounding across accruals |
| Recognized after  | 10,000,863 — 10.000863 USDC                                                         |
| Drip              | 102 base units — equal to the cap, exact                                            |
| Real balance      | 110.000001 USDC — the ceiling the drip climbs toward                                |

The drip equals the cap exactly: each accrual recognizes at most recognized-base × maxRate × elapsed, and the enlarged recognized base becomes the next accrual's base — recognition compounds across accruals. The 200%/year constant is a per-accrual ceiling on that base, not a fixed multi-year schedule; a long-drip projection needs simulation, not extrapolation. Gains drip in; the same mechanism makes losses instant — a real balance below the recognized figure binds withdrawals immediately. Asymmetric by design, in the depositor's favor on losses and against premature gain-harvesting.

### Findings

<table><thead><tr><th width="92">#</th><th>Finding</th></tr></thead><tbody><tr><td>F1</td><td>The role machinery executes as documented: setCurator → submit → execute lands the allocator flag; the <code>setIsAllocator</code> timelock defaults to zero.</td></tr><tr><td>F2</td><td>The inflation attack is dead at zero rate: victim shares equal fair shares exactly, the gift never enters share math.</td></tr><tr><td>F3</td><td>The same-block and immediate inflation sequences are dead at the 200%/year cap: the gift is unrecognized at the victim's deposit — the recognition-timing window those sequences need does not open.</td></tr><tr><td>F4</td><td>A gift to an untouched vault is invisible: <code>totalAssets</code> reads zero with 100 USDC inside; the first deposit opens at the virtual-share floor.</td></tr><tr><td>F5</td><td>Gain recognition is rate-limited and exact: the drip equals old × maxRate × elapsed to the base unit; losses bind immediately.</td></tr><tr><td>F6</td><td>The virtual-share shield (10¹²) and the rate limiter compose into a two-layer inflation defense — the rounding window closed, and the recognition-timing window closed in the immediate sequences measured.</td></tr></tbody></table>

### Limitations

* Three vault sizes on the scale of the experiment wallets; the shield and limiter behavior at production scale with continuous deposits is not measured here.
* The 200%/year cap is the ceiling of the parameter space, chosen to stress the limiter; production caps will sit far lower, which only lengthens the drip.
* The timed inflation sequence — gift, wait, repeated accrual, victim deposit, attacker redeem — is unmeasured; the rate limiter delays recognition, it does not permanently prohibit it.
* The timelock ran at the fresh-vault zero default here; the production-delay wall (Morpho's listing guidance calls for ≥ 3-day timelocks on vault and adapter) and the full dance are measured in Experiment IX.
* No fuzzing of share arithmetic in this experiment — dust and rounding behavior is measured in Experiment II; a stateful fuzz campaign remains forward work.
* Allocator misuse — a malicious or compromised allocator reallocating depositors' funds across markets — is not exercised; the production design's guardrails are documented in the product page.

### Artifacts

<table><thead><tr><th width="179">Artifact</th><th>Value</th></tr></thead><tbody><tr><td>Frozen vault</td><td><a href="https://sepolia.basescan.org/address/0xB2cf495A73C6a4e6bddB8dE166F66Ec3B0B537Db"><code>0xB2cf495A73C6a4e6bddB8dE166F66Ec3B0B537Db</code></a> — maxRate 0</td></tr><tr><td>Active vault</td><td><a href="https://sepolia.basescan.org/address/0xE023094C790a66AF12C5b00074D2daD69667ACe6"><code>0xE023094C790a66AF12C5b00074D2daD69667ACe6</code></a> — maxRate 200%/year</td></tr><tr><td>Empty vault</td><td><a href="https://sepolia.basescan.org/address/0xbB1D316DC28b2b2C733CB210343B6553Abc82a11"><code>0xbB1D316DC28b2b2C733CB210343B6553Abc82a11</code></a> — maxRate 200%/year, no depositors</td></tr><tr><td>virtualShares</td><td>10¹² — verified on all three</td></tr><tr><td>Accrue transaction</td><td><a href="https://sepolia.basescan.org/tx/0x6f32127a309c932ad078a8549e487a26a82a435e05688e6db37834e1eef3fb6f"><code>0x6f32127a…1eef3fb6f</code></a> — drip 102, elapsed 162 s</td></tr><tr><td>Constants</td><td>Attacker 1 base unit · victim 10 USDC · gift 100 USDC · cap 200%/year</td></tr><tr><td>Run window (UTC)</td><td>2026-08-30 – 2026-08-31</td></tr></tbody></table>

### References

**Series**

* nutUSD Testnet Experiment — Experiment I
* nutUSD Adversarial Experiment — Experiment II
* nutUSD Liquidation Envelope — Experiment III
* nutUSD Liquidity & Rates — Experiment IV
* nutUSD Production Recipe — Experiment VI
* nutUSD — product page

**Protocol documentation**

* Vault V2: [https://docs.morpho.org/developers/contracts/morpho-vaults-v2/](https://docs.morpho.org/developers/contracts/morpho-vaults-v2/)
* Roles & capabilities: [https://docs.morpho.org/curate/concepts/roles/](https://docs.morpho.org/curate/concepts/roles/)
* VaultV2 source: [https://github.com/morpho-org/vault-v2](https://github.com/morpho-org/vault-v2)
* ERC-4626 inflation attack literature: [https://github.com/d-xo/weird-erc20](https://github.com/d-xo/weird-erc20) and the OpenZeppelin ERC4626 documentation

> ⚠️ **Experimental Memefi.** No intrinsic value, no expectation of financial gain. Entertainment only — nut responsibly. 🌰
