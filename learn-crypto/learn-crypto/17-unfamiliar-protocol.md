# 17 - Unfamiliar Protocol

Sooner or later you will encounter a protocol that is not Coinbase, Uniswap, Balancer, Aerodrome, or anything else covered directly in this series.



That is where transferable judgment matters.

> **Do not ask “Is this protocol safe?” Ask what it does, what authority it needs, what it depends on, and how failure reaches you.**



***

## 🧱 Start from mechanism, not branding

Classify the thing before interacting.

Is it primarily:

* a token;
* DEX;
* wrapper;
* vault;
* lending market;
* bridge;
* staking system;
* oracle-dependent product;
* derivative;
* smart account;
* router or aggregator?

The label tells you which failure questions to ask.

A polished interface tells you almost nothing about the mechanism.



***

## 🔎 Establish identity

Before connecting a meaningful wallet:

{% stepper %}
{% step %}
### Find the canonical source

Start from official documentation, a known repository, or another independently verified project source.

Do not make a search advertisement your trust root.
{% endstep %}

{% step %}
### Verify the domain

Check spelling and domain structure. Bookmark canonical domains you use repeatedly.
{% endstep %}

{% step %}
### Locate deployed contracts

Compare the protocol's published Base addresses with BaseScan.
{% endstep %}

{% step %}
### Identify the actual action

Determine which contract, asset, and function the interface will ask your wallet to authorize.
{% endstep %}
{% endstepper %}

Identity comes before economics.

There is no reason to study the APY of a contract you have not identified.



***

## ⚙️ Inspect control surfaces

Ask:

<table><thead><tr><th width="181">Control</th><th>Question</th></tr></thead><tbody><tr><td><strong>Owner/Admin</strong></td><td>Who has privileged authority?</td></tr><tr><td><strong>Upgradeability</strong></td><td>Can logic change after you deposit?</td></tr><tr><td><strong>Pause controls</strong></td><td>Can withdrawals or operations be halted?</td></tr><tr><td><strong>Oracle</strong></td><td>What determines external prices?</td></tr><tr><td><strong>Custody</strong></td><td>Which contract or party controls deposited assets?</td></tr><tr><td><strong>Dependencies</strong></td><td>Which tokens, bridges, protocols, or services must continue working?</td></tr><tr><td><strong>Permissions</strong></td><td>What approvals or signatures does the protocol require from you?</td></tr></tbody></table>

None of these properties automatically condemns a protocol.

They tell you where authority and failure can live.



***

## 🧪 Audits and code evidence

An audit is evidence.

Read it as evidence.

Check:

* who performed it;
* what contracts were in scope;
* which code revision was audited;
* when it happened;
* what findings remained unresolved;
* whether the deployed contracts correspond to the reviewed architecture.

Do not compress all of that into:

```
AUDITED ✅
```

Open-source and verified contracts improve inspectability.

They do not prove correctness.



***

## 💰 Then inspect the economics

Once identity and control are understood, ask:

* Where does yield come from?
* What assets are at risk?
* What happens when price moves?
* How deep is exit liquidity?
* Is leverage involved?
* Can collateral be liquidated?
* Are rewards mostly emissions?
* What assumptions keep the system solvent?
* Who bears losses if those assumptions fail?

A protocol can be technically sound and economically terrible.

It can also be economically sensible and technically vulnerable.

You need both analyses.



***

## ✍️ Preview the authority

Before signing:

```
expected action
      ↓ compare
wallet request
      ↓ compare
contract address
      ↓ compare
simulation / decoded effect
```

If the protocol asks for broader authority than the action appears to require, understand why before proceeding.

Do not normalize surprise.

{% hint style="warning" %}
A wallet connection, token approval, Permit-style signature, and state-changing transaction are different authorizations. An unfamiliar protocol is the worst place to stop distinguishing them.
{% endhint %}



***

## 🧯 Limit the experiment

For a protocol you have decided to test:

{% tabs %}
{% tab title="Capital" %}
Use an amount whose loss does not compromise the rest of your portfolio.
{% endtab %}

{% tab title="Wallet" %}
Use an account appropriate to the protocol's trust level. Do not expose long-term storage merely for convenience.
{% endtab %}

{% tab title="Allowance" %}
Constrain token permissions where practical and review them after the experiment.
{% endtab %}

{% tab title="Exit" %}
Test the withdrawal or unwind path before scaling.
{% endtab %}
{% endtabs %}

This is blast-radius engineering.

It does not turn an unknown protocol into a trusted one.



***

## 🌰 Apply the same method around BASED NUT

If a new application claims it supports NUT or wNUT, the token logo is irrelevant evidence.

Verify:

1. the application;
2. the Base deployment;
3. the token contract it recognizes;
4. the contract it asks you to approve;
5. the economic operation;
6. the exit path.

BASED NUT does not make an external integration canonical merely because the integration supports its assets.



***

## 🚩 Stop conditions

Stop when:

* canonical contracts cannot be found;
* deployed bytecode or proxy structure conflicts with documentation;
* ownership or upgrade authority is deliberately obscured;
* the wallet request differs from the advertised action;
* withdrawal mechanics are unclear;
* the yield source cannot be explained;
* the system depends on a token or bridge you cannot identify;
* social pressure is replacing technical evidence.

Not interacting is a valid technical decision.



***

## 🧪 Expert workflow: interrogate an unfamiliar protocol end-to-end

This is the full due-diligence sequence. Do it **before** connecting a valuable wallet.

{% stepper %}
{% step %}
### Canonicalize identity

Find the project’s official website through multiple independent references. From the official site/docs, find repository links and deployment registries. Record exact domains and contract addresses.
{% endstep %}

{% step %}
### Inspect contracts on BaseScan

For every contract your intended action touches, check source verification, proxy/implementation, owner/admin/roles, pause/upgrade controls, age/activity, and relevant ABI functions.
{% endstep %}

{% step %}
### Read security evidence

Locate audits, bug-bounty scope, Immunefi program if one exists, security contacts, incident history, and upgrade policy. Read findings and scope; do not reduce this to an “audited” badge.
{% endstep %}

{% step %}
### Use analytics as corroboration

Check DeFiLlama for protocol/chain TVL, fees, volume, hacks, and category context. Check CoinGecko by **contract address** for token/pool market metadata. Use IQ.wiki for definitions/history/leads. None of these replace canonical deployment evidence.
{% endstep %}

{% step %}
### Query the chain yourself

Use Dune to inspect recent Base transactions, transfers, DEX trades, or protocol-specific decoded events. Look for whether the activity you expect actually exists and whether the frontend’s story matches onchain behavior.
{% endstep %}

{% step %}
### Threat-model the intended action

Write down: origin risk, key/wallet risk, signature/approval risk, contract logic risk, oracle risk, liquidity/market risk, bridge risk, admin/governance risk, frontend/supply-chain risk, and exit risk.
{% endstep %}

{% step %}
### Simulate with a bounded wallet

Use Rabby and optionally Pocket Universe. Connect the **experimental wallet**, not the vault. Reject any request whose contracts, authority, or asset movements you cannot explain.
{% endstep %}

{% step %}
### Perform a minimum-size reversible test

If the protocol passes the research stage, fund the experimental wallet with only the test amount plus gas. Enter, verify on BaseScan, exit, verify again, then inspect/revoke residual approvals with Revoke.cash.
{% endstep %}
{% endstepper %}

***

### Due-diligence worksheet

<table><thead><tr><th width="226">Field</th><th>Required answer</th></tr></thead><tbody><tr><td>Canonical domain</td><td>Exact URL and how independently verified</td></tr><tr><td>Chain</td><td>Exact chain + chain ID</td></tr><tr><td>Contract(s)</td><td>Addresses + canonical deployment source</td></tr><tr><td>Proxy / implementation</td><td>Yes/no; implementation address</td></tr><tr><td>Privileged control</td><td>Owner/admin/multisig/timelock/roles</td></tr><tr><td>Asset identity</td><td>Contract addresses; no ticker-only identity</td></tr><tr><td>Authorization</td><td>Transaction/signature/approval/permit/delegation</td></tr><tr><td>Economic mechanism</td><td>Where value comes from and where it can go</td></tr><tr><td>Price/oracle dependency</td><td>Source and failure mode</td></tr><tr><td>Liquidity/exit</td><td>Exact withdrawal/exit path</td></tr><tr><td>Audits</td><td>Firms, dates, versions/commit scope, unresolved findings</td></tr><tr><td>Bug bounty</td><td>Scope, maximum severity/reward, current status</td></tr><tr><td>Incident history</td><td>What failed and whether architecture changed</td></tr><tr><td>Analytics</td><td>Dune/DeFiLlama/CoinGecko observations + timestamp</td></tr><tr><td>Residual authority</td><td>Allowances/roles remaining after exit</td></tr></tbody></table>



***

## 🔗 Research stack: what each source is for

* [Security Alliance / SEAL](https://frameworks.securityalliance.org/intro/introduction/) — vendor-neutral security framework and operational best practices.
* [BaseScan](https://basescan.org/) — chain-level contract/transaction inspection.
* [DeFiLlama](https://defillama.com/) — comparative analytics and protocol context.
* [CoinGecko](https://www.coingecko.com/) / [API docs](https://docs.coingecko.com/) — contract-oriented token/pool and market-data corroboration.
* [Dune](https://dune.com/) / [Dune Docs](https://docs.dune.com/) — reproducible onchain analytics and DuneSQL.
* [IQ.wiki](https://iq.wiki/) — encyclopedia/context/discovery; promote important claims to primary sources before acting.
* [Immunefi Learn](https://immunefi.com/learn/) / [Research](https://immunefi.com/blog/research/) — exploit, vulnerability, bug-bounty, and security research.
* [The Defiant](https://thedefiant.io/news/defi) — current DeFi news/context; verify operational facts elsewhere.
* [Reddit r/defi — “How do I learn DeFi?”](https://www.reddit.com/r/defi/comments/zlkton/how_do_i_learn_defi/) — community perspectives only; never use anonymous advice as executable authority.
* [Medium — DeFi Security Fundamentals](https://medium.com/@luke101blockchains/defi-security-fundamentals-d9f6f13432d5) — tertiary reading; verify claims independently.



***

## 📐 Final model

```
unknown protocol
      ↓
identify
      ↓
classify
      ↓
inspect control
      ↓
inspect economics
      ↓
inspect authority
      ↓
test small
      ↓
test exit
      ↓
scale only if understanding scales
```

New protocol, same operating grammar.
