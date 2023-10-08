# Transfer

Note: This section is not relevant during the guarded launch.

Sherlock lockTokens (for example lockETH) will be ERC-20 compatible (fungible) in order to increase their liquidity on secondary markets.

The lockTokens will accrue certain amounts of SHERX interest based on how long they have been staked in the pool. If a staker transferred lockTokens that have been in the pool for 1 year to a friend, those lockTokens would be “owed” more SherX than lockTokens that were staked yesterday.

The varying amounts of interest owed to different lockTokens make lockTokens non-fungible (and thus not ERC-20 compatible). In order to fix this, logic has been implemented on lockToken transfers. Basically, all SherX associated with a lockToken is removed on a transfer event. The SherX is not burned, it is moved to the SherX staker pool and the sender address is minted the corresponding amount of lockSherX. This function avoids sending the owed SherX directly to the sender address because this could be a way to “game the system" and get SherX out immediately.
