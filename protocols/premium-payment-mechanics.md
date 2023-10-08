# Premium Payment Mechanics

There will be two inputs that are sent on-chain (from off-chain) for protocol payments:

1. The amount of tokens that a protocol is paying block-by-block
2. The price of the tokens

These values will be updated once a week (for gas efficiency) to ensure the amount of tokens a protocol is paying is roughly in line with the % fee charged on the USD value being covered. Because the token a protocol is paying with (at least during the guarded launch) will be the same token (USDC) in which premiums are denominated, there should be no need for "mid-week updates" to correct any currency fluctuations.

## Examples of mid-week updates

If Sherlock comes to an agreement with a protocol to cover a certain pool for them (instead of a $ amount) and the TVL of that pool changes by a material amount (e.g. due to a whale staking/withdrawing), then Sherlock will update the protocol payment amount to reflect the increased or decreased TVL. During the guarded launch, Sherlock will only write fixed amounts of coverage, so there should be no need for mid-week updates.
