# 🙋 FAQ

## General

### What is Sherlock?

* Sherlock is an audit marketplace and smart contract coverage protocol built on the Ethereum blockchain. Sherlock works to protect Decentralized Finance (DeFi) users from smart contract exploits with security reviews from top auditors backed by smart contract coverage on the audited contracts.

### How is Sherlock different from other audit firms?

* Most audit firms rely on their reputation to convince protocol teams to use them. This alone is a poor way to guarantee incentive alignment. Sherlock provides something far more valuable than just reputation: USDC. If a contract that is audited and covered by Sherlock has a bug bounty payout (or gets exploited), then Sherlock can pay out USDC to reimburse the bug bounty (up to $500k). This incentive demonstrates Sherlocks commitment to do a good job vs. relying on an amorphous reputation across hundreds of audits and dozens of individual auditors.
* Many audit firms charge 100% more than what they pay individual auditors. This is the "reputation premium." Sherlock can pay top independent security experts more than they would make at leading audit firms. Then Sherlock can offer USDC backing behind Sherlock's audit. And the cost can often STILL be lower than what most traditional firms charge.
* Good security work is done by talented individuals. Many audit firms have been known to hide lesser talented individuals behind their overall audit firm reputation. This means the quality of audit you will get from other firms is highly variable. You should always check to see who the individual auditors are. Sherlock is very transparent about the [qualifications of individual auditors](https://audits.sherlock.xyz/leaderboard).

### How is Sherlock different from other risk management protocols?

Coverage is managed by protocols/DAOs instead of users

* Right now, the burden of managing smart contract risk is borne entirely by users. By working directly with protocols, smart contract coverage can be applied to all users with no extra work required. It's very difficult for users to coordinate on a whitehat bug bounty, so this is better managed by the protocol team. Not to mention, when an exploit happens, protocol teams often find themselves deciding to reimburse all users as much as possible, so getting covered at the protocol level helps builders sleep better.

Sherlock can price coverage the lowest because we do the most up-front work

* Because Sherlock requires a full audit from Sherlock before coverage can go live, Sherlock gains more confidence in the security of the smart contracts than anyone else. This allows Sherlock to reward safe protocols for being safe by pricing coverage lower than anyone else can offer.

Claims decisions are made by an unbiased 3rd party

* Follow the incentives. Does a successful payout rely on a decision made by someone who will lose a lot of money if they decide in your favor? Sherlock has partnered with UMA to offer an unbiased claims process handled by objective, third-party voters who have economic guarantees around their incentives. Read more [here](https://docs.umaproject.org/getting-started/oracle).

### How can I get an audit or coverage from Sherlock?

* Please reach out to contact@sherlock.xyz.

### Is coverage for a protocol always fully collateralized?

* One of the superpowers of a risk management protocol like Sherlock is using diversification to increase the affordability of coverage and limit the need for full collateralization. This is what allows coverage to be affordable in traditional markets. The value staked into Sherlock's staking pools is designed to be less than the total funds that Sherlock is covering. By the same token, the staking pool is also designed to be significantly larger than the max size of coverage at any one protocol.
* Isolated exploits should always be 100% paid out. Sherlock is designed to have at least 200% overcollateralization for any singular exploit event.
* Things get more interesting if an exploit occurs at multiple covered protocols and drains 100% of the funds of multiple protocols at the same time. In this situation, depending on the capital efficiency of Sherlock, Sherlock may not be able to reimburse each exploit (assuming 4 or more simultaneous exploits) at 100 cents on the dollar. However, Sherlock's risk models are designed to mitigate the risk of multiple protocols being affected by the same type of exploit. Consequently, it would constitute an extremely unlikely event (never before seen in DeFi) to have multiple covered protocols hacked for nearly all of their TVL at the same time -- but it is theoretically possible.
* Even in extreme scenarios where Sherlock's capitalization falls below the coverage amount for a single protocol, that protocol will only be charged for the amount it would receive in a payout. This ensures that, at any given time, a protocol NEVER overpays for coverage.

### What is a "Best Efforts" audit?

* An audit labeled "Best Efforts" means that the amount of money dedicated to the contest by the protocol team is lower than Sherlock's minimum recommendation. A "Best Efforts" audit is not eligible for coverage from Sherlock afterward. Sherlock offers "Best Efforts" audits because some teams do not have the budget to meet Sherlock's minimum recommended contest cost and Sherlock still wants to do its best to find as many bugs as possible in this codebase instead of leaving these teams to use other (potentially less effective) auditors.&#x20;
