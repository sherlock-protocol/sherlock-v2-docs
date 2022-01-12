# Arbitrage

Sherlock depends on arbitrageurs to make certain mechanisms in the protocol work. In return for this service to the protocol they will earn a small reward. This section explains different ways an arbitrage can be executed.

## arbRestake

> Sherlock.sol

More info: https://docs.sherlock.xyz/stakers/lockup-period#unstaking

The current reward can be viewed using the `viewRewardForArbRestake(id)` function. This will indicate how much USDC will be earned for calling the `arbRestake(id)` function.

This arbitrage will restake positions of owners that don't restake or unstake themselves. This will mitigate the issue that stakers can leave their position in the 'after lockup' state and unstake at the earliest signal of a potential payout.

## forceRemoveByActiveBalance

> SherlockProtocolManager.sol

More info: https://docs.sherlock.xyz/protocols/premiums#maintaining-an-active-balance

This arbitrage can be executed in case `activeBalance(protocol)` get's below `minActiveBalance`. The execution is done by calling `forceRemoveByActiveBalance(protocol)`

The reward for executing this call will be `activeBalance(protocol)`

This arbitrage will remove a protocol that have insufficient balance left.

## forceRemoveBySecondsOfCoverage

> SherlockProtocolManager.sol

More info: https://docs.sherlock.xyz/protocols/premiums#maintaining-an-active-balance

The remaining seconds of coverage of a protocol can be view by calling `secondsOfCoverageLeft(protocol)` in case it's lower than `MIN_SECONDS_OF_COVERAGE` (12 hours) the `forceRemoveBySecondsOfCoverage(protocol)` arbitrage call can be executed.

The reward can be calculated using the following formula

`reward = 1 - (secondsOfCoverageLeft(protocol) / MIN_SECONDS_OF_COVERAGE) * activeBalance(protocol)`

The optimal reward will be when `secondsOfCoverageLeft(protocol)` is equal to `MIN_SECONDS_OF_COVERAGE / 2` (6 hours) as the `activeBalance(protocol)` is slowly decreasing.

This arbitrage will remove a protocol that has insufficient seconds of coverage left.
