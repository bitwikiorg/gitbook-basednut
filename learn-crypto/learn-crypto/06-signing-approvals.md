# 06 - Signing Approvals

DeFi works because your wallet can authorize contracts to do things.

That is also why malicious interfaces want you to sign things.

{% hint style="warning" %}
**Never treat a wallet prompt as a CAPTCHA.**

Read it as a request for authority.
{% endhint %}



***

## 🧩 Four actions beginners confuse

<table><thead><tr><th width="170">Action</th><th>What it means</th></tr></thead><tbody><tr><td><strong>Connect wallet</strong></td><td>Let an interface know your public account and request interactions</td></tr><tr><td><strong>Sign message</strong></td><td>Produce cryptographic authorization without necessarily sending an onchain transaction immediately</td></tr><tr><td><strong>Approve token</strong></td><td>Set an ERC-20 allowance for a spender</td></tr><tr><td><strong>Send transaction</strong></td><td>Broadcast a state-changing instruction to the network</td></tr></tbody></table>

These can appear consecutively in one workflow.

They are not interchangeable.



***

## 💳 ERC-20 allowance

A simplified approval model:

```
owner wallet
    │
    │ approve(spender, amount)
    ▼
token contract
    │
    │ records allowance
    ▼
spender may transfer up to allowance
```

The approval does not necessarily move tokens at the moment it is created.

It changes what the spender can do later.

{% hint style="warning" %}
If you approve a malicious spender for a large allowance, keeping your recovery phrase secret does not undo that authorization.
{% endhint %}



***

## 🎚️ Exact vs large allowances

{% tabs %}
{% tab title="Exact / limited" %}
Permission is constrained near the amount you intend to use.

**Benefit:** smaller exposure if the spender is malicious or later compromised.

**Cost:** future interactions may require another approval and more gas.
{% endtab %}

{% tab title="Large / unlimited" %}
Permission can cover repeated future use.

**Benefit:** fewer approval transactions.

**Cost:** larger persistent authority remains with the spender.
{% endtab %}
{% endtabs %}

There is no universal rule that every large approval is malicious. Legitimate protocols use them for convenience and gas efficiency.

The correct question is whether you understand and accept the scope of the permission.



***

## 🪪 Verify the spender

Before approving NUT, WETH, USDC, or another token:

{% stepper %}
{% step %}
## Verify the protocol origin

Start from a canonical Uniswap, Balancer, Aerodrome, or BASED NUT link.
{% endstep %}

{% step %}
## Read the wallet prompt

Identify the token and requested spending cap.
{% endstep %}

{% step %}
## Verify the spender address

Compare it with official protocol information or trusted explorer labeling where appropriate.
{% endstep %}

{% step %}
## Adjust the allowance if needed

If the wallet supports custom spending caps, choose a scope consistent with the intended action.
{% endstep %}

{% step %}
## Confirm approval separately from the next operation

After approval succeeds, the swap, deposit, or other action may still require its own authorization.
{% endstep %}
{% endstepper %}



***

## 📝 Permit and Permit2 signatures

Modern DeFi can use signed messages to authorize token-related actions.

For example, current Uniswap flows may use Permit2 signatures in addition to approval transactions.

The important lesson is not memorizing Permit2 internals yet.

It is this:

```
no gas prompt ≠ no authority
```

A signature can be economically meaningful.

Read what is being signed.



***

## 🧪 Simulation helps, but it is not an oracle

Some wallets and security tools simulate a transaction before you sign and show expected balance or permission changes.

Use that information.

Do not outsource judgment to it.

A simulation can be incomplete, stale, or misleading under some conditions. SEAL recommends simulation for non-trivial transactions while also warning that simulation itself is not infallible.

A strong review combines:

```
known origin
+ expected contract
+ decoded request
+ simulation
+ wallet/device display
```

If those views disagree, reject the request and investigate.



***

## 🔓 Revocation

An allowance can generally be reduced or revoked with another onchain action.

Revocation is not the same as disconnecting a website.

```
disconnect site
    ≠
revoke token allowance
```

After experimenting with new protocols, periodically inspect active allowances and remove permissions you no longer want.

Revocation itself normally requires gas because it changes onchain state.



***

## 🚨 If the prompt surprises you

Reject it.

Examples:

* You intended to connect, but the wallet requests a signature.
* You intended to swap 10 units, but the allowance is enormous.
* The spender is unfamiliar.
* The website claims the signature is “just verification,” but the wallet decodes token permissions.
* You intended to use Base, but the request is on another network.
* The wallet cannot explain a meaningful transaction and you cannot independently decode it.

SEAL's wallet-security framework captures the principle cleanly: **never sign blindly**.



***

## 🌰 BASED NUT exercise

The next time you swap a BASED NUT ecosystem asset:

1. Record whether an approval appears.
2. Identify which token is being approved.
3. Identify the spender.
4. Identify the allowance.
5. Distinguish the approval from the swap.
6. Verify both on BaseScan if both are onchain transactions.

The lesson is not “approvals are bad.”

The lesson is:

> **Permissions are part of your financial position.**



***

## 🧪 Operational lab: inspect, constrain, and revoke an allowance

Use **Rabby + BaseScan + Revoke.cash**. This exercise teaches the difference between a wallet connection, a signed message, an ERC-20 approval, and the later transaction that consumes that authority.

{% stepper %}
{% step %}
## Generate an approval from a known DEX

From a canonical Uniswap/Balancer/Aerodrome interface, prepare—but do not immediately submit—a small swap using a token that requires approval.
{% endstep %}

{% step %}
## Read Rabby’s request

Identify the token contract, spender, allowance amount, network, and whether the request is an onchain approval or an offchain signature/permit.
{% endstep %}

{% step %}
## Verify the spender independently

Use the protocol’s canonical deployment documentation and BaseScan to identify the spender. Do not approve an address merely because the frontend displays a familiar logo.
{% endstep %}

{% step %}
## Prefer bounded authority for the lab

If the interface/wallet permits an exact or limited allowance, use a small bounded amount. Large or unlimited allowances trade convenience for a larger persistent authorization surface.
{% endstep %}

{% step %}
## Find the allowance on Revoke.cash

Open `https://revoke.cash/` from your bookmark, connect the **training wallet**, select Base, and locate the approval. Cross-check token and spender addresses.
{% endstep %}

{% step %}
## Revoke and verify

Submit the revocation if appropriate. Then verify the revocation transaction on BaseScan. A revocation changes allowance; it does not withdraw assets already deposited into a protocol.
{% endstep %}
{% endstepper %}

{% hint style="danger" %}
**Never “verify” or “synchronize” a wallet by entering a seed phrase.** No legitimate approval checker, support agent, block explorer, or protocol needs your recovery phrase.
{% endhint %}



***

## 🔗 Learn more

* [SEAL — Signing & Verification](https://frameworks.securityalliance.org/wallet-security/signing-and-verification/signing-verification/)
* [Revoke.cash](https://revoke.cash/)
* [Revoke.cash Learn](https://revoke.cash/learn)
* [Pocket Universe](https://www.pocketuniverse.app/)
* [Uniswap Developers](https://developers.uniswap.org/docs)
* [Uniswap Permit2](https://docs.uniswap.org/contracts/permit2/overview)
* [CertiK — DeFi Security Best Practices](https://www.certik.com/blog/top-10-defi-security-best-practices) — supplemental security perspective, not a guarantee that an audited protocol is safe



***

## 📐 Final model

```
authority granted
      =
who can act
    ×
what they can do
    ×
which asset
    ×
how much
    ×
how long the authority remains useful
```

Read the permission before you become the permission.
