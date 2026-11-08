# Permissions

## Permissions

ROOTSTOCK uses role-based permissions for administrative operations inherited from the Balancer v3 authorization model. The exact role assignments are deployment facts and must be generated from the ROOTSTOCK Authorizer/permission configuration.

### Permission categories

Typical privileged capabilities can include:

* changing the Vault Authorizer;
* pausing/unpausing the Vault during the permitted window;
* pausing/unpausing pools according to factory/pool rules;
* enabling/disabling recovery mode under defined conditions;
* setting static swap fees or fee managers;
* configuring protocol/pool-creator fee percentages;
* managing registry entries/aliases;
* administering canonical factories/hooks/supporting contracts.

A deployed contract exposing a function does not mean governance/admin can necessarily call it; the Authorizer mapping determines actual capability.

### Principle of least privilege

Roles should be scoped to the smallest set of actions required. A fee manager does not need authority to replace the Authorizer. A pause role does not need treasury withdrawal authority.

### Permission inventory

Publish a generated table per chain:

| Action ID / function | Target contract | Authorized account/role | Controller type          | Notes   |
| -------------------- | --------------- | ----------------------- | ------------------------ | ------- |
| _generate_           | _generate_      | _generate_              | _multisig/timelock/etc._ | _scope_ |

Do not maintain this table by hand when it can be generated from deployment state.

### Change monitoring

Permission changes are security events. Monitor and alert on:

* role grants/revocations;
* Authorizer replacement;
* owner/admin transfers;
* registry changes;
* fee-manager changes;
* pause/recovery role changes.

### User interpretation

A pool can be non-custodial while still containing configurable parameters. The correct question is not “is there governance?” but **what can each role change, for how long, and can users exit safely?**

### Current pack status

The connected project sources did not expose ROOTSTOCK's deployed Authorizer table. Therefore no account addresses or role holders are asserted here.
