# Staking APY

### Fixed vs. Variable APYs

As mentioned in the [Overview](https://docs.sherlock.xyz/stakers/overview), stakers receive APY from 3 sources:

1. Premiums from protocol customers
2. Interest earned from depositing staker funds into yield strategies (Aave, Compound etc.)
3. Incentive rewards paid in SHER (Sherlock’s governance token)

The first two sources of APY are variable:

1. The premiums from protocol customers are generally a fixed amount (unless the protocol's TVL is lower than their coverage amount). But anytime the USDC amount provided by stakers changes, the APY to any individual staker changes. 
2. Unless Sherlock targets fixed-rate yields, the APYs received from external yield strategies (Aave, Compound, etc.) will fluctuate. 

The third source of APY is variable in $ terms, but fixed in SHER token terms:

3. Any staker will be able to see exactly how many SHER tokens they will receive from staking. If a staker doubles the length of the stake (from 3 months to 6 months), the amount of SHER tokens to be received will double as well. In this way, stakers will have a good sense of the value they're guaranteed to receive by locking up their USDC. Of course, the APY from SHER tokens will fluctuate as the price of SHER fluctuates. 

### How are the SHER tokens for each stake calculated?

In short, the amount of SHER tokens disbursed for a stake depends on 3 factors:
1. The amount of USDC already staked
2. The amount of staked USDC targeted by Sherlock governance
3. The size of the stake

![SHER distribution curve](https://i.imgur.com/1U3ibuR.png)

All stakes that end before point A are paid the maximum amount of SHER per USDC staked.

All stakes that start before point B receive some amount of SHER per USDC staked. Any USDC staked beyond point B receives no SHER tokens. 

Points A and B will be set by Sherlock governance to strategically maintain the desired level of staked USDC over time in order for Sherlock to meet its potential obligations (i.e. payouts) to covered protocols. 

Points A and B may not be visible in the UI, but any staker will know exactly how many SHER tokens they will receive before they stake. 
