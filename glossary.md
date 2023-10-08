# Glossary

## Sherlock Terminology

### Cooldown

* In order to remove a staked funds from a staking pool, a user must first activate the cooldown period. This period represents the time between the activation (or intention to remove the stake) and the time at which the stake is actually released from the protocol.

### Coverage

* If funds at a protocol are covered, it means that Sherlock will reimburse the funds in the event of an exploit (as long as the exploit falls is a covered event according to the coverage agreement).

### "First Money Out" Pool <a href="#buffer-for-stakers" id="buffer-for-stakers"></a>

* This is the pool of tokens that needs to be completely liquidated (in the event of a hack on one of Sherlock's covered protocols) before any staker tokens can be used to pay out the hack. This pool of money is "protection" for stakers. The entire pool is "junior" to the staking pools in terms of liquidation priority. Most or all of the tokens in this pool will be contributed by the Sherlock protocol (from fees) as an added protection for stakers. Deductibles at covered protocols can also serve as protection for stakers.

### Harvesting

* When a user stakes tokens into a staking pool, they earn SherX. As SherX accumulates over time, it may make sense to stake the SherX itself (into the SherX staking pool). This will allow the staker to begin to earn SherX on their staked SherX. Harvesting is the act of taking the SherX earned on the original stake and staking it so it can accumulate SherX as well. Note: Harvesting will likely not be turned on during the guarded launch. Harvesting will still be possible, it will just accrue no interest.

### lockToken

* The token that represents a staker's proportional claim to the tokens in a Sherlock staking pool. See the [lockTokens section](tokens/locktokens.md) for more info.

### Premium

* The amount a protocol pays Sherlock. In return, Sherlock reimburses covered exploits experienced by the protocol.

### Recover

* When the unstake window expires, a user needs to "recover" their position. This is because the user has transferred their lockTokens to Sherlock in order to prepare for unstake. If an unstake does not occur in the window, a user must call "recover" in order to get their lockTokens back and continue accruing interest. Importantly, once this function has been called, the tokens are still in the staking pool and it is necessary to activate the cooldown period again in order to attempt another unstake.

Note for developers: Recover actually refers to the unstakeWindowExpiry() function in our smart contracts.

### SHER

* Sherlock's governance token. See the [SHER section](tokens/sher.md) for more info. The SHER token has not been launched yet.

### SHERX

* A tokenized version of interest paid to stakers from protocol premiums. See the [SHERX section](tokens/sherx.md) for more info.

### Staking

* The act of depositing money into a Sherlock staking pool. Once money has been deposited, tokens accrue to the depositor in the form of APY. A portion of tokens in the staking pools are at risk of being liquidated due to an exploit at one of the protocols covered by Sherlock.

### Unstaking

* The act of removing money from a Sherlock staking pool. This action can only be taken once the cooldown period for the stake has expired.
