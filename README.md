# Intro to Sherlock

Sherlock is an audit marketplace and smart contract coverage protocol built on the Ethereum blockchain. Sherlock works to protect Decentralized Finance (DeFi) users from smart contract exploits with security reviews from top auditors backed by smart contract coverage on the audited contracts. 

You can find a brief overview of the Sherlock ecosystem below.

## Sherlock Ecosystem

There are 3 main participants in the Sherlock ecosystem:

1. Protocols
2. Stakers
3. Security team

![](https://i.imgur.com/bQxJd02.png)

### Protocols

Protocols come to Sherlock for audits from top independent security experts. Sherlock offers smart contract coverage on any contracts that are reviewed as part of the audit. Sherlock offers coverage on white-hat bounties and/or black-hat exploits. The coverage is optional, but adding the coverage allows protocols to know that Sherlock has "skin in the game" in terms of auditing the smart contracts. Basically, if the audited smart contracts have a critical bug, Sherlock will likely have to pay out millions of dollars. No other auditor offers this kind of backing for their audits. 

In return, whenever an exploit occurs at the protocol (on an audited contract), Sherlock will repay the amount of the exploit up to the coverage limit. Sherlock's [claims process](claims/claims-process.md) will decide whether or not an exploit falls under coverage and should be paid out.

### Stakers

Stakers deposit USDC into the staking pools in return for one of the highest USDC APYs (as of 6/18/22) in DeFi. The APY stakers will receive is made up of 3 streams:

1. Premiums from protocol customers
2. Interest earned from depositing staker funds into yield strategies (Aave, Compound etc.)
3. Incentive rewards paid in SHER (Sherlock’s governance token)

In return for these streams, a staker’s funds are at risk of being partially paid out (up to 33%) if a significant covered event (i.e. exploit) occurs on one of the audited contracts covered by Sherlock. Despite the risk, stakers are incentivized to stake because:

1. There is a healthy APY to be earned for doing so
2. Sherlock's auditors are some of the top security experts in the space
3. Each covered protocol is required to have a large bug bounty program which can further protect stakers against losses

### Security Team

Sherlock’s Watsons (the security experts) do a full audit of each prospective protocol's contracts and provide input as to the risk of the protocol's contracts. For security team incentive alignment, we pay out a certain amount of SHER tokens if the protocol a security team is in charge of pricing/securing stays safe over time.

If stakers are well-compensated by a protocol’s fees (net of hacks), then the security team gets rewarded. If hacks eat away most or all of the premiums paid to stakers, the security team responsible for that protocol makes far less. Once a relationship has been initiated with a protocol, Sherlock's Watsons will work closely with the protocol’s developers to maintain and improve the security of the protocol as it changes over time.
