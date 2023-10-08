# lockTokens

A lockToken is simply the "receipt" for staking a certain token with Sherlock.

For example, if a staker stakes 100 USDC into Sherlock's staking pools, the staker would receive a certain amount of lockUSDC in return. The lockUSDC represents the staker's proportional stake in the USDC pool. A staker's lockUSDC balance will not necessarily correspond 1:1 with the amount of USDC staked. For example, 20 lockUSDC could correspond to 100 USDC.

LockUSDC (or any other lockToken) is fungible and ERC-20 compatible.
