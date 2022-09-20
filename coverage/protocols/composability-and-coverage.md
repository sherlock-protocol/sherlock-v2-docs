# Composability and Coverage

Sherlock recognizes that composability and a protocol’s need to integrate with other projects is a valuable part of the DeFi ecosystem. However, for the security of Sherlock’s staking pool, and consequently its covered customers, Sherlock needs to take a slightly risk-averse approach to how integrations are covered.

Both extremes seem unrealistic to expect. It’s unreasonable to _only_ cover integrations that are done with protocols previously audited by Sherlock. However, it’s equally unreasonable to expect Sherlock to cover any integration that a protocol could work with. So, Sherlock is taking an incremental approach, where the covered integrations will include a whitelisted set of protocols, as well as any protocol that has previously been audited by Sherlock.

The current list (which will update) includes: Aave, Compound, Curve, Uniswap, Maker, Lido, Rocket Pool, Balancer, Euler, Primitive, Hook, Lyra, Opyn, Perennial, Element, Merit Circle's Sphere Market, Tempus, Liquifi, Notional (certain contracts), Harpie, Sentiment, NiftyOptions, and FIAT DAO.

If the uncovered protocol has coverage from Sherlock or another coverage provider, and a payout takes place (or is scheduled to take place) for that protocol, and the Protocol Customer receives reimbursement from that payout, then the total amount possible to be paid out to the Protocol Customer will be netted against the first payout. This is to ensure that Sherlock doesn’t pay the same affected party double their loss amount.
