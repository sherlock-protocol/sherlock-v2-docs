# How Collaborative Audits Work

Collaborative Audits are Sherlock’s staffed review engagements for high-stakes scopes. They are designed for teams that need depth, direct coordination with reviewers, and fix verification before release. The work runs in a shared audit workspace that tracks scope, findings, remediation status, linked fixes, and fix review through to a final report.

<br>

### Team assembly

Collaborative Audits are staffed dynamically. Sherlock assembles an engagement-specific review team based on your system’s architecture, attack surface, languages, and release risk. The goal is to match reviewer strengths to the parts of the scope that matter most, rather than applying a fixed team template to every engagement.

<br>

### The timeline

Sherlock aligns with your team on what is in scope, what is out of scope, and what matters most for the release. This includes repositories and languages, deployment context, actors and trust assumptions, and any prior audit history you want carried forward.

#### 2) Quote

Sherlock proposes staffing and a review window based on scope size and risk. Once scheduled, dates and logistics are confirmed, and your team is added to the audit workspace.

#### 3) Audit preparation

Before review begins, your team provides the materials that let reviewers move quickly:

* target repository access and the planned freeze point (commit / branch)
* auditor-facing documentation (system overview, core flows, actors/roles)
* build, compile, and test instructions
* any prior audit reports or relevant historical context

Sherlock confirms audit readiness 3 days before the start date when you provide the frozen commit and final scope list.

#### 4) Audit

The audit team performs a coordinated review and logs issues in the workspace as they are found. Each issue is written for engineering: impact, exploit path, and remediation guidance. Your team stays available for clarifying questions during the review window.

#### 5) Issues review and remediation

This phase turns findings into a remediation plan and verified fixes. Your team confirms issues, records fix intent, links remediation PRs, and schedules fix review once patches are ready. Sherlock reviewers then validate the patch set to confirm issues are resolved and to check that changes did not introduce new risk.

#### 6) Audit report

After fix verification, Sherlock publishes the final report. The report reflects the validated issue set, severity decisions, and fix verification status, and serves as the record for internal sign-off and release readiness.



### Audit readiness checklist

To begin on schedule, the items below must be complete by the start date. Sherlock confirms readiness 3 days before the audit begins, when you provide the frozen commit and final scope.



#### Codebase sizing and pricing

Final pricing is determined by the size of the codebase at the frozen commit hash.

For Solidity scopes, size is measured using nSLOC via solidity-metrics (Solidity Metrics). For non-Solidity scopes, Sherlock sizes the review based on program structure, attack surface, and integration complexity.

Sizing notes:

* includes libraries and imports; excludes interfaces and standard well-known imports
* complexity can change review effort (inline assembly, patterned code, heavy integrations)



#### Frozen code and release alignment

Your code must be frozen 3 days before the audit start.

If you plan to rely on post-audit coverage programs, review assumptions need to match what ships:

* changes between audit and mainnet deployment should be limited to security-related fixes from the audit
* each fix should be made in a separate PR for traceability
* if additional changes are made after the audit, Sherlock may require a follow-up review window for the modified code



#### Tests and documentation

**Testing:**

* 100% passing tests and a target of >80% test coverage at the frozen commit
* clear instructions to run tests and coverage in a clean environment (typically in README.md)

**Documentation:**

* auditor-facing documentation at the start of the audit
* begin with an ELI5 overview, then describe core flows and contract relationships
* list system actors and their intended roles/capabilities
* a formal spec is optional but helpful for invariants and accounting

**Build readiness:**

* clear instructions to build and compile the project
* compilation warnings/errors should be resolved or explicitly explained

**Prior context:**

* prior audit reports for the system should be shared with the review team

**Team availability:**

* your team should be available during the audit window for questions
* schedule fix review promptly once patches are ready



### Audit philosophy

The goal of a collaborative audit is to ship a safer system shortly after the review window.

High-severity issues must be remediated and verified before sign-off. Lower-severity items are handled with judgment based on exploitability and real-world impact. The focus is on issues that change risk, and on fixes that can be verified before release.
