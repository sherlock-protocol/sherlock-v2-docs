# Overview

A staker deposits USDC into Sherlock's staking pool for a fixed term (3 months, 6 months, etc.) and receives a market-beating APY in exchange for the risk of funds being used (up to 33%) to pay out an exploit at a covered protocol.&#x20;

The APY for a staker is made up of 3 streams:

1. Premiums from protocol customers
2. Interest earned from depositing staker funds into yield strategies (Aave, Compound etc.)
3. Incentive rewards paid in SHER (Sherlock’s governance token)

In return for these streams, a staker’s funds are at risk of being partially liquidated (up to 33%) if a covered exploit occurs at a protocol covered by Sherlock (or possibly a protocol that the covered protocol depends on). Despite the risk, stakers are incentivized to stake because:

1. They are paid a handsome APY for the risk
2. They see the quality and incentive alignment of the security team
3. Each covered protocol should have a deductible amount as well as a bug bounty program which can further protect stakers against losses
