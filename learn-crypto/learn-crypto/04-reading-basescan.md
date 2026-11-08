# 04 - Reading Basescan

A wallet tells you what an application thinks happened.

BaseScan lets you inspect what the chain recorded.



You do not need to become a block-explorer archaeologist. You do need enough literacy to stop treating the interface as the sole source of truth.

> **Verification should survive the disappearance of the frontend.**



***

## 🧭 What to inspect first

When you open a Base transaction, locate:

<table><thead><tr><th width="209">Field</th><th>Question</th></tr></thead><tbody><tr><td><strong>Transaction hash</strong></td><td>Which transaction am I inspecting?</td></tr><tr><td><strong>Status</strong></td><td>Did it succeed or revert?</td></tr><tr><td><strong>From</strong></td><td>Which account authorized it?</td></tr><tr><td><strong>To / Interacted With</strong></td><td>Which account or contract received the call?</td></tr><tr><td><strong>Value</strong></td><td>Was native ETH transferred?</td></tr><tr><td><strong>Token transfers</strong></td><td>Which ERC-20 assets moved?</td></tr><tr><td><strong>Transaction fee</strong></td><td>What did execution cost?</td></tr><tr><td><strong>Input data / method</strong></td><td>What contract function or calldata was submitted?</td></tr></tbody></table>

Do not infer everything from a single token-transfer row. A complex swap may involve multiple contracts and transfers.



***

## 🌰 Inspect your own address

{% stepper %}
{% step %}
### Copy the address from Rabby

Use the wallet itself.
{% endstep %}

{% step %}
### Search it on BaseScan

Confirm you are on the Base explorer, not another chain's explorer.
{% endstep %}

{% step %}
### Compare balances

Look at native ETH and token holdings.
{% endstep %}

{% step %}
### Find a known transaction

Open a transfer or swap you personally initiated.
{% endstep %}

{% step %}
### Reconstruct the action

Identify sender, target, assets moved, fee, and status.
{% endstep %}
{% endstepper %}

If you cannot reconstruct your own simple transfer, do not move on to complicated contract interactions yet.



***

## 🪪 Contract identity beats ticker identity

Anyone can deploy a token with a familiar name or symbol.

Therefore, when you see “NUT,” “USDC,” “WETH,” or another ticker, the question is not merely:

> Is the symbol correct?

The question is:

> Is this the canonical contract on the correct network?

Use canonical project documentation to obtain important contract addresses. Then inspect those addresses on BaseScan.

Search engines, token lists, and social posts are discovery tools—not canonical identity proofs.



***

## ⚙️ Read vs write

Verified contracts on explorers often expose contract interaction panels.

{% tabs %}
{% tab title="Read" %}
Read functions query state. They generally do not require an onchain state-changing transaction.

Examples include checking balances, allowances, configuration, or stored parameters.
{% endtab %}

{% tab title="Write" %}
Write functions submit transactions that can change state.

Examples can include approvals, transfers, deposits, wraps, withdrawals, or administrative actions depending on the contract.
{% endtab %}
{% endtabs %}

A direct explorer interaction can be useful when a frontend is unavailable, but it is not inherently safer. You must still understand the function and contract.



***

## 🧩 Proxy contracts

Some systems use proxy patterns where the address you interact with delegates logic to another implementation contract.

That means “verified contract” can require a second question:

> Where does the executable logic live, and can it change?

Do not assume every contract is immutable.

When the explorer identifies a proxy, inspect the implementation and administrative model if the risk matters to your position.



***

## 🚨 Diagnosing failures

{% stepper %}
{% step %}
### Stop retrying automatically
{% endstep %}

{% step %}
### Confirm you are on the intended chain
{% endstep %}

{% step %}
### Verify the target contract
{% endstep %}

{% step %}
### Check whether the transaction was an approval or the intended operation
{% endstep %}

{% step %}
### Check token balance
{% endstep %}

{% step %}
### Check allowance
{% endstep %}

{% step %}
### Check native ETH for gas
{% endstep %}

{% step %}
### Inspect the revert information if decoded
{% endstep %}

{% step %}
### Reconstruct what the interface attempted
{% endstep %}
{% endstepper %}

A classic example is approving an ERC-20 allowance and assuming the swap itself happened. Approval and swap are separate actions in many flows.



***

## ⚠️ BaseScan is a lens, not an oracle

Explorers decode and present blockchain data for humanfs.

Their labels can be helpful, but labels and tags are metadata.

The underlying address, transaction, logs, calldata, and state are more fundamental.

Use labels as convenience, not as your only verification.



***

## 🧪 Operational lab: reconstruct one transaction from raw evidence

Use **Rabby + BaseScan** first.

{% stepper %}
{% step %}
### Start with a known transaction

In Rabby, open the history for your training address and copy the transaction hash of a transfer you recognize.
{% endstep %}

{% step %}
### Open the hash on BaseScan

Search the exact hash on `https://basescan.org/`. Record: status, block, timestamp, `from`, `to`, value, transaction fee, and token-transfer events.
{% endstep %}

{% step %}
### Separate the transaction target from token movement

The transaction’s `to` address may be a router or contract while emitted token-transfer events show different assets moving among several addresses. Do not equate “transaction recipient” with “final token recipient.”
{% endstep %}

{% step %}
### Inspect a contract page

Open a contract address involved in the transaction. Check whether source is verified, whether BaseScan identifies a proxy, and whether the `Contract` tab exposes readable ABI/source information.
{% endstep %}
{% endstepper %}



***



## 🔗 Learn more

* [BaseScan](https://basescan.org/)
* [Etherscan Information Center](https://info.etherscan.com/) — explorer concepts shared across the Etherscan family
* [Dune Docs](https://docs.dune.com/)
* [DuneSQL query language](https://docs.dune.com/query-engine/Functions-and-operators/)
* [CoinGecko API Docs](https://docs.coingecko.com/) — useful later for market/contract lookup corroboration, never a replacement for canonical project identity

## 📐 Final model

```
frontend says what it intended
wallet shows what it requested
BaseScan shows what was recorded
```

For meaningful transactions, learn to use all three.
