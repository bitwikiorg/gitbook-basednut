# 05 - Sending Tokens

Sending is the simplest irreversible operation in crypto.

That makes it the ideal place to build disciplined habits.

> **A transfer is easy to execute and difficult to undo.**



***

## 🎯 Define the transfer completely

Before sending, identify:

```
asset
network
recipient
amount
gas asset
```

If any one of those is ambiguous, the transfer is not ready.



***

## 🧪 The two-transfer method

{% stepper %}
{% step %}
## Verify the recipient independently

Get the address from the intended recipient, your own wallet, or another authoritative source—not an unsolicited message.
{% endstep %}

{% step %}
## Paste, then re-check

Compare the beginning and end of the pasted address. Clipboard malware exists specifically because people stop checking after copying.
{% endstep %}

{% step %}
## Send a small test

Use the exact network and asset route you intend to use later.
{% endstep %}

{% step %}
## Verify receipt

Check BaseScan and, if another person controls the destination, ask them to confirm.
{% endstep %}

{% step %}
## Send the remainder

Re-verify the destination instead of assuming your previous transaction history cannot be poisoned or misread.
{% endstep %}
{% endstepper %}

***

## 🌐 EVM addresses create a dangerous convenience

The same-looking `0x...` address can exist across Base, Ethereum, Optimism, Arbitrum, and other EVM networks.

This reduces friction.

It also makes network mistakes less visually obvious.

A valid-looking address does not prove the recipient expects the asset on Base.



***

## 🌰 Sending NUT

When sending NUT:

* Confirm Base is active.
* Obtain the canonical NUT contract from BASED NUT documentation.
* Confirm the amount.
* Keep enough ETH for gas.
* Verify the transaction after execution.

Do not manually add zeroes based on token decimals unless you are interacting at a low-level contract interface and understand the unit conversion.

Wallet interfaces usually display human-readable units for ordinary transfers.



***

## 🚩 Address poisoning

Attackers can create transaction-history entries involving addresses that resemble addresses you regularly use.

The attack depends on one bad habit:

> copying a destination from history without independently verifying it.

Do not identify an address by the first four characters alone.

Saved contacts and allowlists can reduce repeated manual entry, but they are only as trustworthy as the process used to create them.



***

## 🧠 Receiving is also an operation

When somebody wants to send you an asset, communicate:

1. Your exact address.
2. The intended network.
3. The intended asset if ambiguity exists.

Do not merely send:

```
0x...
```

and assume the sender knows which network you meant.



***

## ⚠️ “Max” deserves suspicion

Wallets may offer a Max button.

For ERC-20 transfers, maxing the token may still leave native ETH for gas.

For native ETH, the wallet must reserve enough to pay the transaction fee.

The interface should estimate this, but do not build the habit of reflexively sending maximum balances.

You will later see the same problem in swaps and bridges.



***

## 🔎 Verify the final state

After sending:

```
sender balance decreased
recipient balance increased
gas paid in ETH
transaction recorded on Base
```

If the wallet UI lags, verify with the block explorer before repeating the transaction.

Repeatedly resubmitting because “the balance didn’t update” can create a second problem.



***

## 🚫 What not to do

* Do not send a large amount as the first test of an address.
* Do not trust only a QR code from an unverified source.
* Do not copy an address from a random explorer label or social post.
* Do not assume the network from the address format.
* Do not send recovery phrases or private keys to prove ownership.
* Do not retry blindly when a transaction appears delayed.



***

## 🧪 Operational lab: execute and audit a test transfer

Use **Rabby** to authorize; use **BaseScan** to verify. If Pocket Universe is installed, treat its preview as an additional comparison surface.

{% stepper %}
{% step %}
## Obtain the recipient out-of-band

For this exercise, use a second address you control or a trusted recipient. Obtain the address from a source independent of the message or website asking you to send.
{% endstep %}

{% step %}
## Start the transfer in Rabby

Select the intended Base account and asset. Paste the recipient. Compare the first and last characters against the independently obtained address.
{% endstep %}

{% step %}
## Send a minimal test

Enter an amount small enough that losing it would be an acceptable debugging cost. Review network, token, recipient, amount, gas, and any simulation preview.
{% endstep %}

{% step %}
## Verify on BaseScan

Open the resulting hash on BaseScan. Confirm success, sender, recipient, token contract, amount, and final balance change.
{% endstep %}

{% step %}
## Only then send the remainder

Repeat the address comparison. A successful test proves the route worked once; it does not justify skipping verification on the larger transfer.
{% endstep %}
{% endstepper %}

***

## 🔗 Learn more

* [SEAL — Verifying Standard Transactions](https://frameworks.securityalliance.org/wallet-security/signing-and-verification/verifying-standard-transactions/)
* [Rabby](https://rabby.io/)
* [Pocket Universe](https://www.pocketuniverse.app/)
* [BaseScan](https://basescan.org/)
* [CoinsBench — DeFi Security 101](https://coinsbench.com/defi-security-101-a-beginners-guide-96fb2033b6df) — supplemental community article; verify incident/mechanism claims against primary sources



***

## 📐 Final model

```
verify destination
      ↓
verify network
      ↓
verify asset
      ↓
test
      ↓
confirm onchain
      ↓
scale
```

Make the cheap transaction prove the expensive transaction's route.
