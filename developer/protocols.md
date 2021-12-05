# Protocol Manager

## Adding a protocol

Protocols start their lifecycle by being added using `protocolAdd()`, the same parameters are expected as `protocolUpdate()`, except for the `protocolAgent`. The `protocolAgent` address is used in the claims process and is able to withdraw active balance of a protocol.

## Setting the premium

Once the protocol is added it is expected to deposit an active balance. Once the balance is deposited the premium can be set using `setProtocolPremium()`.

The premium is subtracted from the active balance per second and claimable by the stakers and non-stakers.

## Being removed

The protocol is expected to keep an active balance over time, this requires to call `depositToActiveBalance(protocol,amount)` every now and then.

Protocols can lose their coverage in 3 different ways

1. Removal by governance
2. Removal by arb using insufficient balance
3. Removal by arb using insufficient seconds of coverage left

> Protocols are still able to submit a claim for 7 days after being removed.

### Removal by governance

A protocol can be removed by governance at any time. The remaining balance is sent to the `protocolAgent`.

### Removal by arb using insufficient balance

If the active balance of the protocol goes below `minActiveBalance`, an arb can call `forceRemoveByActiveBalance(protocol)` and receive the remaining balance.

### Removal by arb using insufficient seconds of coverage left

The protocol is expected to keep a balance that's sufficient to keep active coverage for more then `MIN_SECONDS_OF_COVERAGE`.

Once the active coverage time gets below `MIN_SECONDS_OF_COVERAGE` an arb can call `forceRemoveBySecondsOfCoverage(protocol)` to remove the protocol.

The arb will receive x% of the remaining balance. x is calculated using a linear formula starting at 0% and ending at 100% where the starting point is the time when 'coverage left' == `MIN_SECONDS_OF_COVERAGE` and the end point is when 'coverage left' is equal to 0 seconds. This process takes 12 hours and the peak reward will be at the 6 hour mark (50%) as the active balance of the protocol is simultaneously decreasing over time.

## Edge case accounting error

> This will affect stakers in the core contract, it will not affect non-stakers.

As described above the incentives are in place to remove protocols which have the potential to run higher debt than balance. As this will screw up the accounting. However, it is technically still possible for this edge case to exist: [code](https://github.com/sherlock-protocol/sherlock-v2-core/blob/main/contracts/managers/SherlockProtocolManager.sol#L309)

If this scenario happens stakers could be negatively affected either way (as it could mint less shares or burn excessive USDC) but the contract tries to withhold the `insufficientTokens` by subtracting them from the claimable tokens for the stakers. If that doesn't work, it emits an `AccountingError` event with `insufficientTokens` > 0. The contract expects `insufficientTokens` to be transferred to the contract to make the accounting work again.
