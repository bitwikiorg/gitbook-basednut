# wNUT | Wrapped NUT Observatory | BASED NUT

The Wrapped Leaf of the Root

NUT, wrapped. One root — **supply 1, forever** — in two liquid states: the native **NUT** and **wNUT**, its ERC-20 wrapper. Every wNUT is a receipt for exactly one NUT locked in the wrapper — 1:1, audited, no admin. wNUT opens the Orchard to Balancer v3 composability through Sunflower Grove.

* Wrapper
* ERC-20
* 1:1 Backed
* Audit PASS

[📖 Docs](https://docs.basednut.com/) [🔍 Basescan](https://basescan.org/token/0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3)

## Contracts

| Contract       | Address                                      |
| -------------- | -------------------------------------------- |
| wNUT contract  | `0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3` |
| Underlying NUT | `0xb8de15fb529d98c93c749de63c749d48d25a30df` |

[↗](https://basescan.org/token/0xBA5ED46e31F80dafF307cbf60bd422a6f62E3dd3)

[↗](https://basescan.org/token/0xb8de15fb529d98c93c749de63c749d48d25a30df)

## ⚖️ How much of NUT is wrapped?

One root, two liquid states. The wrapper holds NUT 1:1 against every wNUT in circulation — the backing ratio is the invariant that should always read **exactly 1.00**.

| Metric               | Value | Description             |
| -------------------- | ----- | ----------------------- |
| wNUT supply          | ...   | wNUT                    |
| NUT backing          | ...   | NUT                     |
| Backing ratio        | ...   | NUT per wNUT            |
| Backing value        | ...   | —                       |
| Wrapped share of NUT | —     | Base RPC                |
| Backing surplus      | — NUT | must stay 0             |
| Est. market cap      | —     | wNUT supply × NUT price |
| Data source          | —     | —                       |

## 🔁 Wrap / unwrap flows

Every mint and burn on the tape. **Wrap** = NUT in, wNUT out. **Unwrap** = wNUT in, NUT out. Transfers move the same receipts between holders. Net flow = wrapped − unwrapped.

### Last 24h

| Metric      | Value | Description   |
| ----------- | ----- | ------------- |
| Wrapped     | —     | NUT → wNUT    |
| Unwrapped   | —     | wNUT → NUT    |
| Transferred | —     | wNUT → wNUT   |
| Net flow    | —     | wrap − unwrap |
| Events      | —     | —             |

### Last 7 days

| Metric      | Value | Description   |
| ----------- | ----- | ------------- |
| Wrapped     | —     | NUT → wNUT    |
| Unwrapped   | —     | wNUT → NUT    |
| Transferred | —     | wNUT → wNUT   |
| Net flow    | —     | wrap − unwrap |
| Events      | —     | —             |

### Last 30 days

| Metric      | Value | Description   |
| ----------- | ----- | ------------- |
| Wrapped     | —     | NUT → wNUT    |
| Unwrapped   | —     | wNUT → NUT    |
| Transferred | —     | wNUT → wNUT   |
| Net flow    | —     | wrap − unwrap |
| Events      | —     | —             |

## 📍 Where is the wNUT?

The wrapped supply is a conserved ledger too — every wNUT sits somewhere: pooled as liquidity in Sunflower Grove, or held in wallets.

...

## 🌻 Verified wNUT markets

Sunflower Grove — six Balancer v3 weighted pools, each grafting 20% wNUT rootstock with two 40% scions. Verified on Base; experiment-scale seeds, zero-fabrication rule: no observed swaps yet, so no liquidity/volume numbers shown.

## 🐿️ Largest holders

wNUT is young — a handful of addresses hold the whole crop. Balances read live from Base RPC.

...

## 🧾 Recent events

The raw event tape, oldest first. Wrap = mint from zero. Unwrap = burn to zero. Everything else is a transfer.

...

{% hint style="warning" %}
## 📦 ⇄ 🎁 · The wrapper should always explain itself

Wrap with **depositFor**. Unwrap with **withdrawTo**. **Do not send NUT directly to the wrapper contract** — direct transfers create surplus the wrapper can never return to you. Every metric on this page is read live from the chain; if a source fails, the page says so instead of inventing numbers.
{% endhint %}

_BASED NUT is an experimental memefi project. BASED NUT TOKENS are whimsical meme coins devoid of any intrinsic value or anticipation of financial gains. Coins are for entertainment purposes only. No formal team or roadmap. Please nut responsibly!_
