# Composability and Coverage

Sherlock recognizes that composability and a protocol’s need to integrate with other projects is a valuable part of the DeFi ecosystem. However, for the security of Sherlock’s staking pool, and consequently its covered customers, Sherlock needs to take a slightly risk-averse approach to how integrations are covered.

Both extremes of composability/integrations are problematic. On one extreme, it’s unreasonable for Sherlock to _only_ cover integrations that are done with protocols previously audited by Sherlock. However, it’s equally unreasonable to expect Sherlock to cover any integration under the sun. So, Sherlock is taking an incremental approach, where the covered integrations will include a whitelisted set of protocols, as well as any protocol that has previously been audited by Sherlock.

The current list (which will be updated periodically) can be found [here](https://github.com/sherlock-protocol/integrations-whitelist/commit/b343edd5d6d1f44e11abfc75c63240c6fc546081).&#x20;

If the uncovered protocol has coverage from Sherlock or another coverage provider, and a payout takes place (or is scheduled to take place) for that protocol, and the Protocol Customer receives reimbursement from that payout, then the total amount possible to be paid out to the Protocol Customer will be netted against the first payout. This is to ensure that Sherlock doesn’t pay the same affected party double their loss amount.\
\
In the event of a covered smart contract exploit or economic exploit, the Protocol Customer can submit a claim and be reimbursed for lost on-chain funds up to the stated Active Coverage Amount at the start block of the exploit. If for any reason the affected user(s) or affected protocol(s) see a partial or full return of the exploited funds before or after a payout from Sherlock, the returned funds must be deducted from the Sherlock payout and any amount paid out by Sherlock relating to the returned funds that had been lost (as part of a claim) must be returned to Sherlock.
