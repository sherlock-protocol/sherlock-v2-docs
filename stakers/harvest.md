# Harvest

Note: This section is not relevant during the guarded launch because no APY will be paid to the SHERX pool.

If a staker stakes ETH into Sherlock's staking pools, they will start earning SherX tokens. These SherX tokens will accrue in the pool. They don’t physically accrue since they haven’t been minted yet, but Sherlock's internal accounting will accrue them block-by-block to the ETH pool and thus proportionally to any ETH staker. SherX tokens in the pool will be available to pay out exploits. They will also be included in the staking pools' size calculation. The only difference between interest earned in SherX and staked tokens is that users are not compensated for keeping earned SherX tokens in the pool (they aren’t paid SherX on their SherX). It’s actually in a staker’s best interest to withdraw their SherX tokens as soon as possible (since they are available to pay out exploits but not earning interest).

Because of this dynamic, Sherlock has a harvest function where users can transfer their SherX into the SherX pool, and they will earn SherX on their staked SherX. The harvest function makes it so a staker doesn’t have to wait 7 days (due to the cooldown) to unstake their SherX tokens and then restake them. They can start earning SherX on their previously earned SherX immediately, they just have to spend the gas to call the harvest function.
