---
icon: swap-arrows
---

# Wrap NUT ↔ wNUT

{% hint style="danger" %}
## Critical Warning

:warning: **Do not transfer NUT directly to the wNUT contract!**



All NUT sent directly to contract will be innacessible. You will lose all NUT directly sent to the contract. The wrapping function is done by interacting with the contract like we are detailing in this page.



Use:

**NUT → `approve()` → wNUT → `depositFor()`**



To reverse it:

**wNUT → `withdrawTo()` → NUT**



You need a small amount of **ETH on Base** to pay transaction gas.
{% endhint %}

## How to Wrap NUT ↔ wNUT Using BaseScan

### Contracts

**NUT**\
`0xb8DE15Fb529d98C93C749De63c749D48D25A30DF`

**wNUT**\
`0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3`

Both tokens use **18 decimals**.



Wrapping is **1:1**:

* `1 NUT → 1 wNUT`
* `0.001 NUT → 0.001 wNUT`
* `0.00003478 NUT → 0.00003478 wNUT`



BaseScan contract inputs use **raw integer units**:

`raw amount = NUT amount × 10^18`

Example:

`0.00003478 NUT = 34780000000000`&#x20;



{% hint style="info" %}
## Simple unit converter

Use this as a reference to help you calculate it and revise it: [https://eth-converter.com/](https://eth-converter.com/) .\
\
Treat 1:1 NUT/ETH for the calculator.
{% endhint %}

***

## 🌰 NUT → wNUT

Wrapping requires **two transactions**:

1. Approve the wNUT contract to spend your NUT.
2. Deposit the NUT into wNUT.



### Step 1 — Approve NUT

Open the NUT contract on BaseScan:

`0xb8DE15Fb529d98C93C749De63c749D48D25A30DF`

[https://basescan.org/address/0xb8DE15Fb529d98C93C749De63c749D48D25A30DF#writeContract](https://basescan.org/address/0xb8DE15Fb529d98C93C749De63c749D48D25A30DF#writeContract)

Go to:

**Contract → Write Contract → Connect to Web3**

> **Connect your wallet and make sure you have the right link**

Find:

#### `approve`

Enter the based nut wrapper contract address:

**spender**\
`0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3`



**amount**\
Enter the amount of NUT you want to wrap in raw units (wei).



Example for `0.00003478 NUT`:

`34780000000000`



Click **Write** and confirm the transaction.

Wait for the approval transaction to succeed.



#### Important

The **spender must be the wNUT contract**: `0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3`  and NOT your address!

Approving another address will cause `depositFor()` to fail with:

`ERC20: insufficient allowance`



***

### Step 2 — Wrap NUT

Open the wNUT contract:

`0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3`

[https://basescan.org/address/0xba5ed46e31f80daff307cbf60bd422a6f62e3dd3#writeContract](https://basescan.org/address/0xba5ed46e31f80daff307cbf60bd422a6f62e3dd3#writeContract)

Go to:

**Contract → Write Contract → Connect to Web3**

> **Connect your wallet and make sure you have the right link**

Find:

#### `depositFor`

It has two parameters:

**account**\
Your wallet address.

This is the address that will receive the wNUT.

**value**\
The raw amount of NUT to wrap.



Example:

`34780000000000`

Click **Write** and confirm.



The contract transfers the approved NUT from your wallet into the wrapper and mints the same quantity of wNUT to the `account` address.



Example:

`0.00003478 NUT → 0.00003478 wNUT`

***

## 🔄 wNUT → NUT

Unwrapping requires **one transaction**.



You do **not** need to approve NUT.



Open the wNUT contract:

`0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3`&#x20;

[https://basescan.org/address/0xba5ed46e31f80daff307cbf60bd422a6f62e3dd3#writeContract](https://basescan.org/address/0xba5ed46e31f80daff307cbf60bd422a6f62e3dd3#writeContract)

Go to:

**Contract → Write Contract → Connect to Web3**

> **Connect your wallet and make sure you have the right link**

Find:

#### `withdrawTo`

Enter:

**account**\
The wallet address that should receive the NUT.

Normally, enter your own wallet address.

**value**\
The amount of wNUT to unwrap in raw units.



Example:

`34780000000000`

Click **Write** and confirm.



The wrapper burns that amount of wNUT from your wallet and returns the same amount of NUT.

Example:

`0.00003478 wNUT → 0.00003478 NUT`

***

## Amount Examples

| NUT / wNUT |        BaseScan value |
| ---------: | --------------------: |
|          1 | `1000000000000000000` |
|        0.1 |  `100000000000000000` |
|       0.01 |   `10000000000000000` |
|      0.001 |    `1000000000000000` |
|     0.0001 |     `100000000000000` |
| 0.00003478 |      `34780000000000` |
|   0.000001 |       `1000000000000` |

***
