---
description: Common Questions for Adding Smart Contract Coverage to Your Protocol
---

# FAQ

**Can I see an example coverage agreement?**

Yes. You can look through an example coverage agreement [here](https://docs.google.com/document/d/1ubWlKWrm0cOIddmvE1srKaAPfXPn9iSatDoylS3mepg/edit?usp=sharing).\
\
**What if we change the contract afterwards?**

Ideally protocol teams will do update audits (through Sherlock) for any code changes that will go to mainnet. Sherlock offers 3-day micro contests for this purpose.&#x20;

But sometimes a protocol isn't able to get code audited before putting it live, so Sherlock will continue to cover the audited contract code even if other code within the contract is changed, but only payouts resulting from exploits that would have been possible without the unaudited, changed code would be eligible for coverage.

New unaudited contracts are not covered by Sherlock, and any payouts resulting from exploits possible in those contracts will not be reimbursed.&#x20;

**Does the audit contest cost include coverage?**

No. Coverage is an additional investment and is completely optional. You can decide to add coverage after the audit is complete.&#x20;

**Does Sherlock offer a bug bounty program?**

Sherlock will help you set up a bug bounty program (through Immunefi) and Sherlock coverage will apply to Critical bug bounty payouts as defined by Sherlock. Bug bounty programs and audits are the best means available to prevent exploits and protect users.&#x20;

**Who qualifies for coverage?**

Protocols that have: (1) completed a "non-best efforts" audit contest with Sherlock and (2) have received a sign-off on every fix completed during the fix review (3) have an nSLOC amount that is acceptable in Sherlock's pricing tables may request coverage from Sherlock. Request an audit [here](https://audits.sherlock.xyz/request-audit).

If the fixes made after a Sherlock audit are extensive, Sherlock and the Lead Senior Watson may recommend an additional follow-up contest. This recommendation does not need to be followed, but it is mandatory to follow the recommendation to receive coverage.&#x20;

**If I don't get coverage after the audit contest, can I get coverage later?**

It depends. Sherlock recommends getting coverage after the audit contest, but it may be possible to get coverage later if no changes were made to the smart contracts covered by Sherlock.

**What is needed to go live with coverage?**

All Sherlock needs to get things live are:&#x20;

1\) Address controlled by your team (i.e. Gnosis multi-sig, MetaMask wallet) that you can send a transaction from so that you can file claims in the future&#x20;

2\) The initial coverage payment. Here's Sherlock multi-sig address for the initial coverage payment: 0x666B8EbFbF4D5f0CE56962a25635CfF563F13161&#x20;

3\) The amount of coverage desired

**How much will monthly premiums cost if we went through a public contest with Sherlock, and got all of our fixes signed-off?**

Sherlock can present a quote to you based on Sherlock's pricing tables. These tables take into account the nSLOC of the codebase that was audited as well as the public/private nature of the audit.&#x20;

**What is the address for the initial coverage payment?**&#x20;

The address (on Ethereum mainnet) for the initial coverage payment is: 0x666B8EbFbF4D5f0CE56962a25635CfF563F13161&#x20;

**Who should get coverage?**

Sherlock recommends coverage to any protocol team that is interested in protecting their users from losses due to exploits. Audits and bug bounty programs are two of the best ways to protect users against losses and coverage can allow protocol teams to afford bigger bug bounties.&#x20;

**I already got an audit from someone else. Can I get coverage with Sherlock?**\
Unfortunately, Sherlock requires protocols to conduct a Sherlock audit contest for the opportunity to qualify for coverage.
