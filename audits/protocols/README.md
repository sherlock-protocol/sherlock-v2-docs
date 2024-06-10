# 🧑‍💻 Protocol Teams

Request an audit [here](https://docs.google.com/forms/d/e/1FAIpQLSfqy21chyyzhAfbCxMQOlNTlYxegfvxZDhYsPkpI\_xD6AQiag/viewform)!

Security is a top priority for high-quality projects shipping code to mainnet given the inherently adversarial nature of on-chain interactions and consequently the prospect of losing user funds. And because Sherlock is willing to offer bug bounty and exploit coverage to qualifying codebases, Sherlock obsesses over the processes to keep codebases safer.

The most well-known process for securing a codebase is an audit.

**An audit in the crypto space usually looks something like this:**

* 2-4 security experts pore over the codebase for a few weeks and flag any vulnerabilities they see.

However, a new approach to auditing has also sprung up and become quite popular: audit contests.&#x20;

**An audit contest usually looks something like this:**

* A protocol team creates a prize pool ($30k-$200k usually), and anyone in the world can submit vulnerabilities to the codebase chosen by the protocol team. The higher the severity, the more of the prize pool the security expert is awarded.

Below, we’ll outline the strengths and weaknesses of both traditional audits and audit contests. Then we’ll propose a third approach that features the “best of both worlds.”

### Traditional Audits

**Strengths**

* You know who is going to audit your code (although far too many auditors don't even tell you that or put it in the audit report)
* You know how long that expert is going to spend trying to find bugs in your codebase
* When the expert finds bugs and the protocol team makes fixes, the expert will verify that the fixes don’t have bugs

**Weaknesses**

* Only 2-4 people look at your code, leaving room for missed bugs (even among top experts)
* They are not cost-effective (\~50% of what you pay does NOT go to security experts)
* They can often take a very long time (3-12 months) to schedule
* There is no direct incentive for an auditor to try their hardest

### Audit Contests

**Strengths**

* The likelihood of missed bugs is [very low](https://docs.google.com/spreadsheets/d/1RIJCK3\_9RHvtNPObsDRTAqkP9IbyutZMsqlKNnZCO00/edit#gid=0) because 200-400 security experts try to find bugs in your code
* Incentives are stronger to find bugs: experts get paid based on the number of findings and severity of findings
* Contests can often be scheduled within days
* You can decide your own price (size of the prize pool)

**Weaknesses**

* There’s no guarantee that any top-tier security experts will look at your code (especially if the contest was scheduled days before)
* Even if top-tier experts participate, you don’t know how long they’ll spend looking for bugs
* Once the bugs are found, there is no one who will help you fix them (no fix review)
* Security experts are often incentivized to spend time submitting unimportant/non-critical findings
* They are inefficient and your money often goes towards admin work and unimportant areas (Low/Informational/QA/gas findings)
* The protocol team is often expected to sort through thousands of issues at the end and any overlooked issue could result in an exploit

### Sherlock's Approach: The Best of Both Worlds

Sherlock’s approach provides a protocol with the focus, collaboration, and assurance of a traditional manual audit, alongside the breadth of security expert participation from an audit contest.&#x20;

**Overview**

* At least 1 Senior Watson (top-ranked security expert) is heavily incentivized (through fixed pay and an ELO-style ranking system) to find as many bugs as possible over the entire length of the audit
* The significant prize pool attracts 200-400 independent auditors who get paid based on the severity of their findings (only High/Medium severity findings are rewarded)
* The Lead Senior Watson comes back to help the protocol team with fixes (provides a 1-day complimentary fix review)
* Sherlock’s decentralized judging process takes hundreds of raw, duplicate issues and turns them into a digestible report, saving the protocol team days of work and reducing the possibility of overlooked vulnerabilities
* Sherlock's process is the most cost-effective: 80% of what you pay to Sherlock goes directly to security experts
* Sherlock is the only auditor to offer bug bounty and exploit coverage after the audit is conducted (once the fix review is finished), ensuring that Sherlock's incentives are aligned in shipping the most secure protocol possible.&#x20;

Sherlock’s unique offering assigns a top-ranked senior security expert (Senior Watson) to act as the lead security auditor throughout the duration of the contest, earning attractive fixed pay alongside the ability to compete for the entire prize pool.

The fixed nature of the lead senior auditor gives protocols the assurance that, at minimum, one highly skilled security auditor will be conducting an in-depth review of the codebase, will be there to discuss issues with the protocol team, and will conduct a half-day fix-review to make sure any fixes have been implemented securely.

The talents of this one individual will be enhanced by the skillset of an unlimited number of independent security experts / teams competing to win a greater portion of the prize pool. And the Senior Watson will only keep their “senior” status as long as they find more vulnerabilities than the rest of the field. And of course, Sherlock's continued commitment to incentive alignment is at the core of a Sherlock audit. Qualifying protocols that go through an audit (and complete the fix review) can add smart contract coverage at any point post-audit to reimburse its users in the event of a hack - helping the protocol team build trust with its early LPs, users and/or community.
