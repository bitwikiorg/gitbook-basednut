# 19 - Exiting

DeFi tutorials disproportionately teach entry.

That is backwards.

> **If you do not know how to exit a position, you do not understand the position.**

Every new action should include its reverse path.



***

## 🔄 Entry and exit pairs

<table><thead><tr><th width="227">Entry</th><th>Exit</th></tr></thead><tbody><tr><td>Buy on Coinbase</td><td>Sell / withdraw fiat according to exchange support</td></tr><tr><td>Withdraw to Base</td><td>Deposit back to supported exchange address</td></tr><tr><td>Swap into token</td><td>Swap out through available liquidity</td></tr><tr><td>Wrap</td><td>Unwrap / redeem</td></tr><tr><td>Add liquidity</td><td>Remove liquidity</td></tr><tr><td>Stake LP position</td><td>Unstake, then remove liquidity</td></tr><tr><td>Supply to lending market</td><td>Withdraw supply</td></tr><tr><td>Borrow</td><td>Repay, then release collateral</td></tr><tr><td>Approve</td><td>Reduce/revoke allowance</td></tr><tr><td>Bridge in</td><td>Bridge/transfer out through a supported route</td></tr></tbody></table>

The reverse action may have different costs, timing, or constraints.



***

## 🧪 Practice the exit early

For a new DeFi primitive:

{% stepper %}
{% step %}
### Enter small

Do not begin with meaningful size.
{% endstep %}

{% step %}
### Verify the position

Confirm balances and onchain state.
{% endstep %}

{% step %}
### Exit part of it

Withdraw, unwrap, remove liquidity, or swap a small amount back.
{% endstep %}

{% step %}
### Verify the exit

Confirm what assets you received and what permissions remain.
{% endstep %}

{% step %}
### Only then consider scaling

You have now tested the complete lifecycle instead of half of it.
{% endstep %}
{% endstepper %}



***

## 💧 Liquidity determines exit quality

Owning a token does not guarantee you can sell it near the last displayed price.

To exit, somebody or some pool must absorb your trade.

As your position becomes large relative to liquidity:

```
position size ↑
relative liquidity ↓
price impact ↑
exit quality ↓
```

This is why market capitalization alone is a poor exit metric.



***

## 🌰 Exiting NUT-related positions

Depending on the actual position, your exit may involve:

* removing NUT/WETH liquidity;
* unstaking an LP position first;
* swapping NUT through Uniswap, Balancer, or Aerodrome;
* unwrapping wNUT;
* transferring assets to another wallet;
* returning supported assets to Coinbase.

Do not assume every position has one-click exit routing.

Inspect the actual contracts and venue.



***

## 🏦 Returning to Coinbase

Before sending assets back to a centralized exchange:

{% stepper %}
{% step %}
### Confirm asset support

Confirm Coinbase currently supports the asset.
{% endstep %}

{% step %}
### Confirm network support

Confirm Coinbase supports deposits of that asset on the selected network.
{% endstep %}

{% step %}
### Verify the deposit address

Generate or verify the current deposit address.
{% endstep %}

{% step %}
### Confirm compatibility

Confirm network compatibility.
{% endstep %}

{% step %}
### Send a test

Send a test if the amount is meaningful.
{% endstep %}

{% step %}
### Wait for confirmation

Wait for the test to credit before sending the remainder.
{% endstep %}
{% endstepper %}

Do not send NUT to Coinbase merely because Coinbase supports Base.

{% hint style="warning" %}
**Network support does not imply support for every token on that network.**
{% endhint %}



***

## 🔓 Exit permissions too

Leaving a protocol does not necessarily remove its allowance.

After closing a position, ask:

```
funds withdrawn?          yes/no
rewards claimed?          yes/no
debt repaid?              yes/no
collateral released?      yes/no
LP unstaked?              yes/no
allowances still active?  yes/no
```

A clean exit includes residual authority.



***

## 🚨 Emergency exits

During market stress or an exploit, your normal exit route may degrade:

* liquidity disappears;
* gas rises;
* frontends go offline;
* protocols pause functions;
* bridges delay;
* oracles behave unexpectedly;
* contracts revert.

That is why learning direct contract/explorer interaction and maintaining gas is operational resilience.

Do not assume an emergency exit is guaranteed.



***

## 🚫 Exit myths

* A quoted price guarantees executable liquidity.
* A token supported on Base is automatically supported by Coinbase.
* Removing liquidity automatically revokes approvals.
* A wrapped token always has instant redemption.
* A protocol frontend must be available to exit.
* “I can always sell later” is a risk model.



***

## 🧪 Operational lab: make exit a precondition, not an afterthought

For every position you currently use or intend to use, create an **exit card** before adding more capital.



### Exit card template

```
Position:
Chain:
Entry contract/interface:
Exit function/interface:
Assets received on exit:
Approvals required to exit:
Expected delay / queue / cooldown:
Liquidity dependency:
Oracle dependency:
Bridge dependency:
Alternative interface if frontend fails:
Where final funds should land:
How final state is verified:
```



### Practice sequence

{% stepper %}
{% step %}
### Choose a position

Choose one small DEX, LP, wrapper, or lending position.
{% endstep %}

{% step %}
### Test the exit

Exit 5–10% if mechanics permit.
{% endstep %}

{% step %}
### Verify the transaction

Verify the exit transaction on BaseScan.
{% endstep %}

{% step %}
### Inspect remaining state

Inspect remaining position state.
{% endstep %}

{% step %}
### Inspect residual approvals

Inspect residual approvals in Revoke.cash.
{% endstep %}

{% step %}
### Verify exchange support

If the final objective is fiat/CEX custody, verify that Coinbase currently supports the asset **and Base network** before sending anything back.
{% endstep %}

{% step %}
### Use a test transfer

Use a test transfer to the exchange when the route is new.
{% endstep %}
{% endstepper %}

{% hint style="danger" %}
Never send a token to Coinbase merely because Coinbase lists the ticker. Confirm the exact asset and supported deposit network in the receiving interface first.
{% endhint %}

***

## 🔗 Learn more

* [Coinbase — Assets on multiple networks](https://help.coinbase.com/en/coinbase/trading-and-funding/sending-or-receiving-cryptocurrency/assets-on-multiple-networks)
* [Revoke.cash](https://revoke.cash/)
* [BaseScan](https://basescan.org/)
* [Base Documentation](https://docs.base.org/)

***

## 📐 Final model

```
understood position
 =
entry
+ operation
+ failure modes
+ exit
+ residual permissions
```

Know where the door is before you walk into the room.
