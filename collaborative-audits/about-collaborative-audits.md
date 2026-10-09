# About Collaborative Audits

### What is a Collaborative Audit?

A Sherlock Collaborative Audit is a private, time-boxed security review carried out by a hand-picked team of auditors. The engagement runs inside GitHub and is tracked through dedicated Sherlock dashboards.

Auditors work together on the codebase, investigate potential vulnerabilities, document validated findings, and review the protocol team’s fixes. The final report is delivered after auditor sign-off.

### Our audit philosophy

The goal of a Sherlock audit is to prepare a protocol for onchain deployment shortly after the engagement.

The review focuses on issues that could break the protocol. High and Medium findings are the main focus of the report. Low-severity findings and informational notes are included where useful, rather than to increase the finding count.

High-severity findings must be corrected and signed off on by Sherlock auditors as part of audit completion.

### How an engagement works

An engagement follows five stages:

1. **Scope and schedule.** The protocol grants repository access and submits its scope through Sherlock’s scoping dashboard.
2. **Freeze and prepare.** The protocol freezes its code three days before kickoff and provides the final commit hash and list of contracts.
3. **Review.** Auditors collaborate in a dedicated GitHub repository, moving from line-level discussions to validated findings.
4. **Fix review.** The protocol submits fixes, and auditors review the changes.
5. **Final report.** After auditor sign-off, Sherlock delivers a report recording the scope, findings, reviewed commits, and remediation outcomes.

See **Scoping & Audit Requirements** for preparation requirements and **Review, Fixes & Reporting** for the engagement workflow.

### How researchers are selected

Sherlock selects researchers whose experience is most relevant to the code in scope. Team selection is based on the best match for the codebase rather than availability.

Selection considers:

* **Language and execution environment:** Such as Solidity/EVM, Rust/Solana, and Bitcoin-adjacent systems.
* **Protocol category:** The type of system and its known failure modes.
* **External integrations:** Such as oracles, multisigs, cross-chain messaging, and other DeFi protocols.
* **Researcher track record:** Verified accuracy, impact, and specialization within Sherlock’s network.

### How auditors collaborate

The audit team works in a shared GitHub repository containing the code at the frozen commit.

Auditors discuss potential issues directly on the relevant lines of code. This allows one researcher to confirm, extend, or rule out another researcher’s lead.

Once a potential issue has a validated attack path and impact, it becomes a GitHub issue documenting the finding.

### Blackthorn

Blackthorn is Sherlock’s elite, exclusive research team and premier audit track.

The team consists of a small group of researchers who have consistently performed at the highest level within Sherlock’s network. Blackthorn is reserved for high-stakes infrastructure where the margin for error is lowest.
