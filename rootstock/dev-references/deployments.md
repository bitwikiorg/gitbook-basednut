# Deployments

Deployments bind ROOTSTOCK's abstract contract roles to **specific chains, addresses, and versions**.

This page is the address authority for integrations. An address found in upstream Balancer documentation, an SDK default, a frontend cache, or an old transaction is not automatically a ROOTSTOCK deployment.

{% hint style="danger" %}
Always scope an address by **chain ID**. The same interface name—or even the same-looking address pattern—does not establish identity across chains.
{% endhint %}

***

### Base Sepolia

**Chain ID:** `84532`

ROOTSTOCK's active application branch contains a Base Sepolia network configuration and patches `@balancer/sdk@6.2.0` with the following deployment addresses. The SDK patch is pinned at ROOTSTOCK commit `de40322e58be81bf31ad30cbaaa14eac37555ce6` (2026-09-26); the Base Sepolia network configuration originated in commit `52190ac058ec8b94e7efb3feb3ba08ad32ecd2e5` (2026-09-22).

#### Core and Routers

| Role                           | Address                                      | Status in current integration   |
| ------------------------------ | -------------------------------------------- | ------------------------------- |
| Vault                          | `0xEf348c4222ab9c08aFE768AD722Fb02b10d640c9` | active Base Sepolia integration |
| Vault Admin                    | `0xC67111C130b1380E5ba027733315DE82bB5A6837` | active Base Sepolia integration |
| Vault Extension                | `0x8e86fDf21a578cDB01F1A58c71a2ef21dBBE2A8E` | active Base Sepolia integration |
| Router                         | `0xDD9793Cd4B79a8bd65D690C64A3074D023Dfa759` | active Base Sepolia integration |
| Batch Router                   | `0x41978EB90477d4D971dF22111B2d09679f4DadA6` | active Base Sepolia integration |
| Buffer Router                  | `0xe1c7A291D4eBa814f36Ec96fD10F343A53BFa1D7` | active Base Sepolia integration |
| Composite Liquidity Router     | `0x5808B214B66C70e6c0759803AbF3498c2c78F437` | active Base Sepolia integration |
| Unbalanced Add Via Swap Router | `0xbbEc9F2c69037852A86aB3F97326172649E82337` | active Base Sepolia integration |

#### Factories and Hooks

| Role                      | Address                                      | Status in current integration   |
| ------------------------- | -------------------------------------------- | ------------------------------- |
| Weighted Pool Factory     | `0x277D7dDe3C6762C31CfB438c9331376fE8887A7c` | active Base Sepolia integration |
| Stable Pool Factory       | `0x24Ab9fBA48E54b05c24a02122C4c40fD2018bA10` | active Base Sepolia integration |
| Gyro ECLP Pool Factory    | `0x6057859CC86AA62c54860e1A342f60ab42098Efe` | active Base Sepolia integration |
| reCLAMM Pool Factory      | `0x928E433f50fa579c9be5f7e1273F1db46D630EE1` | active Base Sepolia integration |
| LBP Factory               | `0xDfDddD87dC49756DD93598123879AE3D67B531a3` | active Base Sepolia integration |
| Fixed Price LBP Factory   | `0x9A30757385012495A21D64c5EfAC335B1A6fE48D` | active Base Sepolia integration |
| Stable Surge Pool Factory | `0x6cD1150ccc00e0D00Cd3f671a8bdf00d38f5BE6e` | active Base Sepolia integration |
| Stable Surge Hook         | `0x581e1dE0C136134AF479d09619b5f950420A427D` | active Base Sepolia integration |
| MEV Capture Hook          | `0x7E50a9dB8252414AAD240E08b9ed4176C4D64888` | active Base Sepolia integration |

#### Shared infrastructure

The current Base Sepolia frontend configuration also uses:

| Role           | Address                                      |
| -------------- | -------------------------------------------- |
| WETH predeploy | `0x4200000000000000000000000000000000000006` |
| Permit2        | `0x000000000022D473030F116dDEE9F6B43aC78BA3` |
| Multicall      | `0xca11bde05977b3631167028862be2a173976ca11` |

These are shared chain/integration dependencies, not ROOTSTOCK-specific protocol contracts.

***

### What this table does not claim

The ROOTSTOCK repository README reports a larger Base Sepolia deployment set. The published application/SDK map exposes **17 v3 protocol addresses** required by the current integration; it is not a complete manifest of every deployed helper, library, authorizer, fee contract, test token, or deployment task.

In particular, the currently published 17-address SDK map does not include a Protocol Fee Controller or Contract Registry address. Those contracts may be discoverable through the deployed Vault or a fuller deployment record, but this page does not invent addresses that are not present in the published 17-address map.

***

### Base mainnet

The ROOTSTOCK frontend supports Base as a product network, but its current Base v3 contract configuration resolves addresses through upstream `@balancer/sdk` `AddressProvider` entries.

Those addresses are **Balancer deployments** and are therefore not listed here as ROOTSTOCK AMM deployments.

{% hint style="warning" %}
Do not interpret “the ROOTSTOCK frontend can run on Base” as proof that a distinct ROOTSTOCK AMM contract set has been published on Base mainnet.
{% endhint %}

The separate nutUSD Morpho vault is outside this AMM deployment table.

***

### Deployment provenance requirements

For each canonical ROOTSTOCK contract, the long-term deployment manifest should publish:

* chain ID;
* contract role/type;
* address;
* protocol/deployment version;
* deployment transaction;
* source commit/tag;
* compiler/build configuration;
* constructor/factory parameters;
* bytecode hash where maintained;
* active/superseded/deprecated state.

Addresses alone are not enough to reproduce or audit a deployment.

***

### Keep history

Never overwrite an old address when a contract is replaced.

A deployment history lets:

* indexers decode old logs correctly;
* wallets identify historical counterparties;
* support tools reproduce old transactions;
* auditors compare migrations;
* applications stop routing new activity to deprecated contracts without losing historical identity.

The current address can move; history should not.
