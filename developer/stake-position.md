# Stake positions

![Stake position lifecycle](https://i.imgur.com/XXzh7bn.png)

## Minting a position

Accounts can call `initialStake(amount, period, receiver)` to stake USDC into Sherlock. The lockup `period` is in seconds but periods need to be whitelisted by governance. At the initial deployment it will be possible to stake for 3, 6 or 12 months.

During the `period` the position can be transferred using the ERC721 interface. But no Sherlock specific action can be executed during the lockup `period`.

## After lockup

After the lockup period expires the following situations can happen

- Owner calls `ownerRestake(id, period)` to restake all USDC for new `period` of time
- Owner calls `redeemNFT(id)` to redeem all USDC and burn the NFT
- If the owner doesn't execute either one of these actions in 2 weeks, any account is able to call `arbRestake(id)` to restake the position.

> SHER rewards will be send to the owner on the first action after every lockup period

## Arb restake

After 2 weeks without action on an unlocked position arbs can come in to `arbRestake(id)`, 20% of the underlying USDC amount (principal + yield) is at risk for the owner of the position. The reward rate moves from 0% of the underlying USDC amount to 20% over the course of 1 week.

The position is restaked for 12 weeks after this call has been executed. At the end of 12 weeks the cycle described in 'after lockup' starts again.

> All owed SHER rewards (from the previous lockup) are still transferred to the owner on `arbRestake()`.
