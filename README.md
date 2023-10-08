# Introduction to Sherlock

Sherlock is a protocol on the Ethereum blockchain that protects Decentralized Finance (DeFi) users from smart contract exploits with proprietary security analysis and protocol-level coverage.

You can find a brief overview of the Sherlock ecosystem below.

## Sherlock Ecosystem

There are 3 main participants in the Sherlock ecosystem:

1. Protocols
2. Stakers
3. Security team

![](https://i.imgur.com/HTmUxBi.png)

### Protocols

Protocols pay Sherlock a small fee in return for repayment in the event of a hack. A protocol will indicate how much value they want insured ($1Bn, a specific pool, etc.), and Sherlock will work with each protocol to tailor a coverage agreement to their unique needs. Then Sherlock's security team will conduct a thorough assessment over the course of a few days or weeks to understand the risks related to a protocol. The security team will work with Sherlock's risk team to determine the pricing for the protocol. If the protocol agrees to the pricing, they will start streaming payment to Sherlock. In return, whenever an exploit occurs at the protocol (within coverage), Sherlock will repay the amount of the exploit up to the coverage limit. Sherlock's [claims process](claims-assessment/deciding-on-payouts.md) will decide whether or not an exploit falls under coverage and should be paid out.

### Stakers

Stakers deposit funds into the staking pools in return for what should be one of the highest APYs in DeFi. Right now, only USDC can be staked, but we may expand this to more currencies in the future. The APY stakers will receive is made up of 3 streams:

1. Premiums from protocol customers (this will eventually be the biggest stream)
2. Interest earned from depositing user stakes on lending protocols (Aave, Compound etc.)
3. Incentive rewards paid in SHER (Sherlock’s governance token)

In return for these streams, a staker’s funds are at risk of being partially liquidated if a significant covered event (e.g. exploit) occurs at one of the protocols covered by Sherlock (or possibly a protocol that the covered protocol depends on). Despite the risk, stakers are incentivized to stake because:

1. They are paid a high and commensurate APY for the risk
2. They see that the security team’s incentives are aligned with theirs
3. Each covered protocol should have a deductible amount as well as a bug bounty program which should further protect stakers from losses

### Security Team

Sherlock’s Watsons (the security team) will do a fundamental assessment of a protocol and provide input to the pricing of coverage (alongside the Sherlock risk team). For security team incentive alignment, we guarantee a certain amount of SHER tokens if the protocol a security team is in charge of pricing/securing stays safe (relative to the pricing they helped inform). The security team will be incentivized to set a floor on the coverage pricing because the bulk of their compensation will depend on the dollar value of hacks vs. the price paid by the protocol for coverage over defined time intervals.

To put it simply, if stakers are well-compensated by a protocol’s fees (net of hacks), then the security team gets rewarded handsomely. If hacks eat away at most or all of the fees to stakers, the security team responsible for that protocol makes far less. Once a relationship has been initiated with a protocol, the security team will work closely with the protocol’s developers to maintain and improve the security of the protocol as it changes over time.
