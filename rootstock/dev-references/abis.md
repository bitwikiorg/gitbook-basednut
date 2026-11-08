# ABIs

An ABI is the machine-readable serialization contract between an application and deployed bytecode. It defines callable functions, events, custom errors, argument types, return types, and mutability—but it does not explain the economic meaning of those values.

For ROOTSTOCK, an ABI becomes canonical only when it is tied to the **same build and deployment** as the address an integration is calling.

***

### ABI and semantic documentation are different layers

Consider a field typed as `uint256`.

The ABI can tell a client how to encode it. The ABI alone cannot tell the client whether that integer represents:

* raw token units;
* scaled18 units;
* a fixed-point percentage;
* a token rate;
* an invariant ratio;
* a maximum bound;
* an RPT amount.

That meaning belongs in interface/API documentation and source comments. Both layers are required.

***

### Minimum ABI set

Publish versioned ABIs for every ROOTSTOCK contract applications are expected to call or decode, including deployed instances of:

#### Core

* Vault;
* Vault Extension / Vault Admin surfaces where separately addressable;
* Protocol Fee Controller;
* Authorizer / permission contracts;
* Contract Registry, when deployed.

#### Routers

* Basic Router;
* Batch Router;
* Buffer Router;
* Composite Liquidity Router;
* Unbalanced Add Via Swap Router;
* aggregator-specific Routers, if deployed.

#### Pools and factories

* standard Pool interfaces;
* Weighted / Stable and other standard factories;
* deployed canonical custom Pool families;
* factory interfaces used for provenance/discovery.

#### Hooks

* `IHooks` / callback interface;
* canonical deployed Hook ABIs;
* Hook-specific read/configuration interfaces where applications need them.

***

### Version every artifact

A filename such as `Router.json` is insufficient once a Router is replaced.

A useful artifact layout is conceptually:

```
artifacts/
  84532/
    router/
      <deployment-version>/
        Router.abi.json
        metadata.json
```

The accompanying metadata should bind the ABI to:

```
chainId
contract role
address
source repository
commit/tag
compiler version
build configuration
bytecode hash
creation/deployment transaction
status: active | superseded | deprecated
```

This is what lets an indexer decode historical transactions after the current alias changes.

***

### Generate; do not transcribe

Do not manually rewrite Solidity signatures into ABI JSON.

The release process should:

1. compile the pinned source tree;
2. export ABI artifacts from that build;
3. bind artifacts to deployment metadata;
4. verify deployed bytecode against the expected build where reproducibility permits;
5. publish the artifacts as an immutable/versioned release.

Manual transcription creates silent drift in tuples, enum representations, overloaded functions, event indexing, and custom-error signatures.

***

### Exact inherited identifiers

ROOTSTOCK conceptual documentation uses **RPT** for Root Pool Token. An inherited ABI may still contain Balancer-era identifier names such as `bptAmountOut` or `getBptRate`.

Do not rename ABI fields/functions in generated artifacts. Code generation, selectors, and downstream tooling depend on exact names and signatures.

***

### Current ROOTSTOCK state

The ROOTSTOCK application consumes `@balancer/sdk` and frontend-level generated/static ABI material, but the public repository does not currently publish a complete generated ABI release tied to the ROOTSTOCK Base Sepolia deployment set.

The Base Sepolia integration therefore establishes supported addresses for the application, but it does not by itself establish a complete canonical ABI pack for those deployed contracts.

{% hint style="warning" %}
Inherited Balancer v3 ABIs are useful for interface lineage. Before treating one as the ABI for a ROOTSTOCK deployment, verify that it matches the deployed ROOTSTOCK bytecode/build.
{% endhint %}

***

### What clients should pin

A typed client should pin **three things together**:

```
chain + deployment/address + ABI/build version
```

Pinning only an npm package is not enough. Pinning only an address is not enough. The decoding/encoding surface must correspond to the contract actually deployed at that address.

See Deployments for addresses and Repositories for code provenance.
