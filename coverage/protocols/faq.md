---
description: Common Questions for Adding Smart Contract Coverage to Your Protocol
---

# FAQ

**Can I see an example coverage agreement?**

Yes. You can look through an example coverage agreement [here](https://docs.google.com/document/d/1ubWlKWrm0cOIddmvE1srKaAPfXPn9iSatDoylS3mepg/edit?usp=sharing).\
\
**What if we change the contract afterwards?**

Ideally protocol teams will do update audits (through Sherlock) for any code changes that will go to mainnet. Sherlock offers 3-day micro contests for this purpose.&#x20;

But sometimes a protocol isn't able to get code audited before putting it live, so Sherlock will continue to cover the audited contract code even if other code within the contract is changed, but only exploits that would have been possible without the unaudited, changed code would be eligible for coverage.

New unaudited contracts are not covered by Sherlock, and any exploits resulting from them will not be reimbursed.&#x20;

**Does the audit contest cost include coverage?**

No. Coverage is an additional investment and is completely optional. You can decide to add coverage after the audit is complete.&#x20;

**Does Sherlock offer a bug bounty program?**

Sherlock will also help you set up a bug bounty program (through Immunefi) and Sherlock will cover up to 200k USDC of a Critical bug bounty payout. Bug bounty programs are highly recommended (may be mandatory soon) for protocol teams looking for Sherlock coverage.&#x20;

**Who qualifies for coverage?**

Protocols that have: (1) completed an audit contest with Sherlock and (2) have received a sign-off on every fix completed during the fix review may request coverage from Sherlock. Request an audit [here](https://docs.google.com/forms/d/e/1FAIpQLSfqy21chyyzhAfbCxMQOlNTlYxegfvxZDhYsPkpI\_xD6AQiag/viewform).

If the fixes made after a Sherlock audit are extensive, Sherlock and the Lead Senior Watson may recommend an additional follow-up contest. This recommendation does not need to be followed, but it is mandatory to follow the recommendation in order to receive coverage.&#x20;

**If I don't get coverage after the audit contest, can I get coverage later?**

It depends. Sherlock recommends getting coverage after the audit contest, but it may be possible to get coverage later if no changes were made to the smart contracts covered by Sherlock.

**What is needed to go live with coverage?**

All Sherlock needs to get things live are:&#x20;

1\) Address controlled by your team (i.e. Gnosis multi-sig, MetaMask wallet) that you can send a transaction from so that you can file claims in the future&#x20;

2\) The initial coverage payment. Here's Sherlock multi-sig address for the initial coverage payment: 0x666B8EbFbF4D5f0CE56962a25635CfF563F13161&#x20;

3\) The amount of coverage desired. Most teams opt for coverage to roughly track their TVL (so that the protocol never overpays for coverage). If this is the case, then Sherlock asks for a methodology for calculating the protocol's TVL periodically (Etherscan contracts, DeFi Llama, etc.)

**How much will monthly premiums cost if: (1) we have $2M TVL, (2) we went through a public contest with Sherlock, and (3) we got all of our fixes signed-off?**

If you want coverage for $2M, and the fixes after completing the Sherlock audit contest have been signed-off on, the monthly premium will be 4% annualized on the TVL which will be \~6,700 USDC per month.&#x20;

**What happens if my TVL is lower than $2M?**

If your TVL starts out lower than $2M, you will only be charged on what your TVL is (assuming you've opted for the coverage to track your TVL).&#x20;

**What is the address for the initial coverage payment?**&#x20;

The address (on Ethereum mainnet) for the initial coverage payment is: 0x666B8EbFbF4D5f0CE56962a25635CfF563F13161&#x20;

**Who should get coverage?**

Sherlock recommends coverage to protocols that are interested in protecting their users from net losses due to exploits (for example, situations where a protocol is exploited and the hacker does not return any funds).

**I already got an audit. Can I get coverage with Sherlock?**\
Unfortunately Sherlock requires protocols to conduct a Sherlock contest audit for the opportunity to qualify for coverage.
