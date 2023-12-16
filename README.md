# 👋 Intro to Sherlock

Sherlock is an audit marketplace and smart contract coverage protocol built on the Ethereum blockchain. Sherlock works to protect Decentralized Finance (DeFi) users from smart contract exploits with security reviews from top auditors backed by smart contract coverage on the audited contracts.

You can find a brief overview of the Sherlock ecosystem below.

## Sherlock Ecosystem

There are 3 main participants in the Sherlock ecosystem:

1. Protocols
2. Stakers
3. Watsons

![](https://i.imgur.com/bQxJd02.png)

### Protocols

Protocols come to Sherlock for audits from top independent security experts. Sherlock offers smart contract coverage on any contracts that are reviewed as part of the audit. Sherlock offers coverage primarily on white-hat bounties, which also includes some coverage on black-hat exploits. The coverage is optional, but adding the coverage allows protocols to know that Sherlock has "skin in the game" in terms of auditing the smart contracts. Basically, if the audited smart contracts have a critical bug, Sherlock will likely have to pay out hundreds of thousands of dollars. No other auditor offers this kind of backing for their audits.

Whenever a Critical-severity vulnerability is discovered in a protocol (on an audited contract), Sherlock may pay for the bug bounty cost (minus a deductible). Sherlock's [claims process](claims/claims-process.md) will decide whether or not the vulnerability falls under coverage and should be paid out.

### Stakers

Stakers deposit USDC into the staking pools in return for an attractive APY. The APY stakers will receive is made up of 2 streams:

1. Premiums from protocol customers
2. Incentive rewards paid in SHER (Sherlock’s governance token)

In return for these streams, a staker’s funds are at risk of being partially paid out (up to 50%) if a significant covered event (i.e. bug bounty payout) occurs on one of the audited contracts covered by Sherlock. Despite the risk, stakers are incentivized to stake because:

1. There is an attractive APY to be earned for doing so
2. Sherlock's audits are some of the best in the space
3. Each covered protocol is required to have a deductible which can protect stakers against losses

### Watsons

Sherlock’s Watsons (the security experts) do a full audit of each prospective protocol's contracts and provide input as to the risk of the protocol's contracts.\
\
Sherlock audits feature both dedicated, top-tier auditors who are incentivized to find vulnerabilities in the codebase, as well as a contest pot where anyone in the world can find bugs. See [protocols](audits/protocols/ "mention") for more info on the audit process. And security experts (or those planning to become security experts) can see more information about how they can participate in audits in [watsons](audits/watsons/ "mention").
