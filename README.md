# Intro to Sherlock

Sherlock is a protocol on the Ethereum blockchain that protects Decentralized Finance (DeFi) users from smart contract exploits with proprietary security analysis and protocol-level coverage.

You can find a brief overview of the Sherlock ecosystem below.

## Sherlock Ecosystem

There are 3 main participants in the Sherlock ecosystem:

1. Protocols
2. Stakers
3. Security team

![](https://i.imgur.com/bQxJd02.png)

### Protocols

Protocols pay Sherlock a small fee in return for repayment in the event of a hack. A protocol will indicate how much value they want insured ($1Bn, a specific pool, etc.), and Sherlock will work with each protocol to tailor a coverage agreement to their unique needs. Then Sherlock's security team will conduct a thorough assessment over the course of a few days or weeks to understand the risks related to a protocol. The security team will collaborate with Sherlock's risk team to determine the pricing for the protocol. If an agreement is reached on pricing, the protocol will start streaming payment to Sherlock. In return, whenever an exploit occurs at the protocol (within coverage), Sherlock will repay the amount of the exploit up to the coverage limit. Sherlock's [claims process](broken-reference) \[update link] will decide whether or not an exploit falls under coverage and should be paid out.

### Stakers

Stakers deposit USDC into the staking pools in return for what should be one of the highest APYs in DeFi. The APY stakers will receive is made up of 3 streams:

1. Premiums from protocol customers
2. Interest earned from depositing staker funds into yield strategies (Aave, Compound etc.)
3. Incentive rewards paid in SHER (Sherlock’s governance token)

In return for these streams, a staker’s funds are at risk of being partially liquidated (up to 33%) if a significant covered event (i.e. exploit) occurs at one of the protocols covered by Sherlock (or possibly a protocol or library that the covered protocol depends on). Despite the risk, stakers are incentivized to stake because:

1. They are paid a handsome APY for the risk
2. They see the quality and incentive alignment of the security team
3. Each covered protocol should have a deductible amount as well as a bug bounty program which can further protect stakers against losses

### Security Team

Sherlock’s Watsons (the security team) do a fundamental security assessment of each prospective protocol and provide input to the pricing of coverage (alongside the Sherlock risk team). For security team incentive alignment, we pay out a certain amount of SHER tokens if the protocol a security team is in charge of pricing/securing stays safe over time (relative to the pricing the Watsons helped inform).

If stakers are well-compensated by a protocol’s fees (net of hacks), then the security team gets rewarded commensurately. If hacks eat away most or all of the premiums paid to stakers, the security team responsible for that protocol makes far less. Once a relationship has been initiated with a protocol, the security team will work closely with the protocol’s developers to maintain and improve the security of the protocol as it changes over time.
