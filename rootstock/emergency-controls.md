# Emergency Controls

## Emergency Controls

Emergency controls are designed to contain damage while preserving a path for liquidity providers to exit. The inherited v3 model combines **time-bounded pausing** with **Recovery Mode** rather than granting an indefinite ability to freeze user funds.

### Pause model

The Vault and pools can expose pause state during configured pause windows. While paused, normal state-changing operations are restricted.

The purpose is operational containment: if a vulnerability is suspected, authorized actors can stop ordinary execution while the issue is investigated.

### Why pause authority is time-bounded

Permanent unilateral pause authority would create a long-term custody/control risk. The upstream v3 design therefore uses finite pause windows and buffer-period mechanics so emergency power can expire.

ROOTSTOCK should verify and publish its actual configured durations rather than copying upstream values blindly.

### Buffer period

If a contract is already paused when its primary pause window expires, an additional buffer period can preserve that paused state long enough to investigate/remediate. After the relevant periods expire, pause authority becomes constrained according to the deployed logic.

### Recovery Mode

Recovery Mode provides a simplified **proportional withdrawal** path intended to remain usable when ordinary pool behavior is unsafe or unavailable.

A crucial inherited safety property is that recovery withdrawal lives at the Vault layer, making the exit mechanism consistent across current and future pool implementations instead of relying on every Pool author to implement it independently.

### Threat model

Emergency controls should protect against both sides:

* **insufficient authority** — inability to stop active exploitation;
* **excessive authority** — governance/admin can indefinitely lock liquidity.

The correct design balances incident response with user exit guarantees.

### Monitoring

Alert immediately on:

* Vault pause/unpause;
* pool pause/unpause;
* recovery-mode enable/disable;
* approaching pause-window expiration;
* changes to accounts authorized for emergency actions.

### Incident documentation

For every emergency action publish exact transaction hashes, affected contracts/pools, time, reason, scope, user impact, and exit instructions.
