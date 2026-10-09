# Scoping & Audit Requirements

### Start with repository access

Scoping begins once the protocol grants the `sherlock-admin` GitHub account access to every repository under review.

The protocol then submits its scope through Sherlock’s scoping dashboard. This submission is used for sizing, pricing, and scheduling.

You do not need a completed, frozen codebase to book an audit. The code must be frozen three days before the audit starts.

### Sizing and pricing

Final pricing and audit length are determined from the codebase at the frozen commit, using `solidity-metrics` and Sherlock’s audit pricing methodology.

The calculation includes:

* In-scope contracts.
* The libraries and imports used by those contracts.

Interfaces and well-known imports, mainly OpenZeppelin libraries, are excluded.

Other factors can affect the audit time, including inline assembly, highly repeated or patterned code, and integrations with other protocols.

The quote is final only at the frozen commit. Scope that grows between booking and the code freeze can change the price.

### Code freeze: three days before kickoff

The protocol must freeze its code **three days before the audit starts**.

At that point, provide:

* The frozen commit hash.
* The final list of contracts to be audited.

Sherlock checks the codebase against the audit requirements at this stage, starting with the test suite.

### Testing requirements

The protocol must have:

* **Greater than 80% test coverage.**
* **100% passing tests.**

Every test must have a way to fail. A test that cannot fail is not considered a valid test.

#### Test instructions

The repository’s `README.md` must explain how to run the tests and measure coverage.

Verify that these instructions work in a clean environment. Auditors use them to run the test suite and understand how the codebase behaves.

### Code commenting

The protocol must use NatSpec commenting with a **greater than 80% comment-lines-to-code-lines ratio**.

Comments within functions and for individual lines are encouraged.

### Documentation requirements

Preliminary documentation describing the system must be available at the start of the audit.

If user-facing documentation is incomplete, provide a shorter auditor-facing document that explains the system.

The documentation should include:

* **A plain-language introduction:** Start with an ELI5 explanation of the protocol’s intended purpose.
* **A contract walkthrough:** Explain the purpose of each contract and how the contracts relate to one another.
* **Actors and permissions:** List every actor in the system and its intended roles and capabilities. For example, explain whether an administrator can mint tokens and whether a depositor has that permission.

#### Documentation versus a specification

Documentation describes what the protocol does at a high level and is required.

A technical specification describes what the protocol should do, including intended behavior, variables, and invariants. A specification is optional but can be useful to both the protocol team and the auditors.

### Build and compilation instructions

Provide instructions for building and compiling the project.

The code must compile. Warnings and errors must be resolved or explained to the auditors before the audit begins.

### Previous audits

Make all previous audit reports for the system available to Sherlock’s auditors.

### Protocol team availability

Protocol engineers must be available throughout the audit window to answer questions and clarify system behavior.

After the audit, the protocol team must be proactive in preparing fixes and scheduling the fix review promptly.

### Readiness review

Sherlock checks the frozen codebase three days before kickoff.

If the codebase does not meet the audit requirements, Sherlock’s auditors may reject it or agree to a smaller scope.

Booking an audit before the codebase is complete does not remove the requirement to meet the readiness criteria for the engagement.
