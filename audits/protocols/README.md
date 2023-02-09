# Protocols

Request an audit [here](https://docs.google.com/forms/d/e/1FAIpQLSfqy21chyyzhAfbCxMQOlNTlYxegfvxZDhYsPkpI\_xD6AQiag/viewform)!

Security is a top priority for high-quality projects shipping code to mainnet given the inherent adversarial nature of on-chain interactions and consequently the prospect of losing user funds. And because Sherlock is willing to write up to $5M of coverage behind every protocol we cover, Sherlock obsesses over the processes to keep codebases safer.

The most well-known process for securing a codebase is an audit.

**An audit in the crypto space usually looks something like this:**

* 2 or 3 security experts pore over the codebase for a few weeks and flag any vulnerabilities they see.

However, a new approach to auditing has also sprung up and become quite popular: audit contests (Code Arena is the most well-known).

**An audit contest usually looks something like this:**

* A protocol publicly releases a codebase, creates a prize pool ($30k-$100k usually), and anyone in the world can submit vulnerabilities. The higher the severity, the more of the prize pool they are awarded.

Below, we’ll outline the strengths and weaknesses of both traditional audits and audit contests. Then we’ll propose a third approach that features the “best of both worlds.”

### Traditional Audits

**Strengths**

* You know who is going to audit your code (and hopefully they have a reputation as an expert)
* You know how long that expert is going to spend trying to find bugs in your codebase
* When the expert finds bugs and the protocol team makes fixes, the expert will verify that the fixes don’t have bugs

**Weaknesses**

* Only 2 or 3 people look at your code, leaving room for missed bugs (even with experts)
* They are usually much more costly (you pay a company to vet talent for you)
* They can often take a very long time (3-12 months) to schedule
* There is no direct incentive for an auditor to do a good job (only indirect reputation)

### Audit Contests

**Strengths**

* The likelihood of missed bugs is [very low](https://docs.google.com/spreadsheets/d/1RIJCK3\_9RHvtNPObsDRTAqkP9IbyutZMsqlKNnZCO00/edit#gid=0) because 50-100 security experts try to find bugs in your code
* Incentives are stronger to find bugs: experts get paid based on the severity of their findings
* Contests can often be scheduled within days

**Weaknesses**

* There’s no guarantee that top-tier security experts will look at your code (especially if the contest was scheduled days before)
* Even if top-tier experts participate, you don’t know how long they’ll spend looking for bugs
* Once the bugs are found, there is no one who will look for bugs in the fixes (no fix review)
* Security experts are incentivized to spend time submitting Low/Informational/QA/gas findings
* The protocol team is expected to sort through hundreds of issues at the end

### The Best of Both Worlds

Sherlock’s approach provides a protocol with the focus, collaboration, and assurance of a traditional manual audit, alongside the breadth of security expert participation in contest models.

**Overview**

* Top-ranked security expert is incentivized (through ELO-style ranking system) to look for bugs over the entire length of the audit
* Significant prize pool attracts 50-100 independent auditors who get paid based on the severity of their findings (only High/Medium findings are rewarded)
* Top-ranked security expert also handles the fix review
* Sherlock’s internal team takes hundreds of raw, duplicated issues and turns them into a digestible report, saving the protocol team days of work

Sherlock’s unique offering assigns a top-ranked senior security expert to act as the lead security auditor throughout the duration of the contest, earning lucrative fixed pay alongside the ability to compete for the entire prize pool.

The fixed nature of the lead senior auditor gives protocols the assurance that, at minimum, one highly skilled security auditor will be conducting an in-depth review of the codebase, will be there to discuss issues with the protocol team, and will conduct a fix-review to make sure all changes have been implemented securely.

The talents of this one individual will be enhanced by the skillset of an unlimited number of independent security experts / teams participating to win a greater position of the prize pool. And the senior security auditor will only keep his “senior” status as long as they find more vulnerabilities than the rest of the field. And of course, at the core of a Sherlock Audit, is our continued commitment to incentive alignment. Every protocol who goes through an audit has the ability to add smart contract coverage at any point post-audit to reimburse its users in the event of an exploit - helping a protocol build trust with its community whether it’s for first-time LPs, or loyal bag holders.
