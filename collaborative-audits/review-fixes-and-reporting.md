# Review, Fixes & Reporting

### Audit workspace

At kickoff, Sherlock creates a dedicated work repository containing the code at the frozen commit.

Sherlock then opens one pull request for each in-scope file.

This structure gives auditors a full-file diff where they can comment on any line. Review progress is visible file by file, and discussions remain attached to the exact code being audited, even if the protocol’s own repository changes.

Out-of-scope code does not receive a review pull request.

### The review process

The review runs in two stages: line-level discussion followed by validated findings.

#### 1. Line-level review

Auditors work through the in-scope files and comment directly on the relevant lines in each pull request.

Comments may include potential issues, questions for the protocol team, invariants to check, and cross-contract interactions to investigate.

Because the team works in the same pull requests, auditors can confirm, extend, or rule out one another’s leads.

#### 2. Validated findings

Once a potential issue has a validated attack path and impact, it is opened as a GitHub issue in the work repository.

The GitHub issue becomes the finding of record. It includes:

* Root cause.
* Impact.
* Severity.
* A proof of concept where relevant.
* A recommended fix.

### Findings and severity

High and Medium findings are the main focus of the report. Low-severity findings and informational notes are included where useful and kept brief.

| Severity            | Treatment                                                                      |
| ------------------- | ------------------------------------------------------------------------------ |
| High                | Must be corrected and verified by Sherlock auditors.                           |
| Medium              | A fix is generally expected. The finding may be acknowledged with a rationale. |
| Low / Informational | The protocol may fix or acknowledge the finding.                               |

Each finding receives a final status in the report, such as **Resolved** or **Acknowledged**.

### Fix window

After the audit closes, the protocol has **three weeks** to return its fixes.

The fix review then runs for **one to three days**, depending on the number of fixes and the amount of refactoring.

The protocol team should schedule the fix review promptly once its fixes are ready.

### Submitting fixes

Map each fix pull request to the finding it addresses. One pull request per fix is recommended.

The fix review described here covers fixes for findings raised by Sherlock auditors.

### What fix review checks

Auditors review whether:

* The fix removes the root cause rather than only addressing the reported attack path.
* The change introduces a new issue in the surrounding code.
* Each finding has an appropriate final status.

High-severity findings must be corrected and signed off on by Sherlock auditors as part of audit completion.

### Final report

The final report is generated after auditor sign-off. It records the original audit scope and the outcome of the fix review.

The report includes:

* **Scope:** The repositories and files included in the review.
* **Code references:** The audited commit hash and the final post-fix commit hash.
* **Engagement details:** The audit window and the auditors involved.
* **Findings:** Each finding organized by severity, with its description, impact, recommendation, and final status.
