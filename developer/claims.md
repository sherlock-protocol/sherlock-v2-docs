# Claims

![Claim lifecycle](https://i.imgur.com/BEjncCz.png)

## Creating a claim

Claims can be created by protocol agents. Protocol agents take actions on behalf of a specific covered protocol. The protocol agent will be the linked to the claim and is able to execute on future actions regarding the claim.

Claims can be submitted for the current and previous coverage amounts of the protocol.

Claims can still be submitted 7 days after coverage has ended.

Only 1 claim can be active per protocol. Each claim has a state (default: nonExistent) associated with it at all times until it is removed and cleaned up.

> Claims can be removed in the SpccPending or SpccDenied stage. After cleaning the previous claim, the protocol agent is able to submit a new claim.

## Sherlock Protocol Claims Committee

After a claim is created, the Sherlock Protocol Claims Committee (SPCC) has 7 days to either approve or deny the claim. On approval the protocol agent is able to call `payoutClaim()`. If the SPCC denies the claim, the protocol agent is able to escalate the claim (if desired) to the UMA Optimistic Oracle.

## Escalate to UMA

The protocol agent has to pay a bond to escalate the claim (20k USDC). This bond will be paid back if UMA approves the claim. If UMA denies the claim the bond will be distributed to Sherlock stakers.

## UMA halt operator

This role can be renounced, but if active this role can block a claim within 24 hours of approval by the UMA OO. In case no action is taken the claim is valid and a payout can be executed after 24 hours. The UMA halt operator role will likely be a multisig controlled by the UMA core team, who can decide if the oracle malfunctioned and block a potentially fraudulent claim result.
