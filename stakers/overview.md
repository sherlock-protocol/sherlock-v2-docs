# Overview

A user stakes in Sherlock's staking pools because they will see an attractive APY made up of 3 streams:

1. Fees from protocol customers (this will eventually be the biggest stream)
2. Interest earned from sweeping funds to Aave, etc.
3. Incentives distributed in SHER (Sherlock’s governance token)

In return for these streams, a staker’s funds are at risk of being partially liquidated if a significant covered event (e.g. exploit) occurs at one of the protocols covered by Sherlock (or possibly a protocol that the covered protocol depends on). Despite the risk, stakers are incentivized to stake because:

1. They are paid a high and commensurate APY for the risk
2. They see that the security team’s incentives are aligned with stakers
3. They are senior to the “first money out” pool and any affected protocol's deductible so staker funds are only at risk once those mechanisms are exhausted.

A staker will only be able to stake in USDC during the guarded launch. A staker will receive lockTokens (for example lockUSDC) in return for staking. LockTokens are the tokens Sherlock mints to represent stakes in a staking pool.

Sherlock's protocol was designed with two important staking considerations in mind:

* Earning interest on a token of the staker's choosing (again, only USDC for the guarded launch)
* Keeping exposure to the staked token over time (instead of exposure to a melting pot of tokens)

## Why not have stakers stake with SHER (Sherlock's governance token)? This could give SHER utility and prop up the price?

The price of SHER is likely to be highly correlated with exploit events on protocols Sherlock actively covers. As soon as there is an exploit at a covered protocol, it’s reasonable to assume SHER’s price will drop. If the staking pools consist entirely of SHER, it’s likely the USD value of the staking pools will shrink right at the moment it needs to repay an exploit.
