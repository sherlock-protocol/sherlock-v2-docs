---
description: >-
  What happens after an audit, including how findings are finalized, how teams
  confirm disposition and implement fixes, and how Sherlock verifies remediation
  before a final report.
---

# Protocol Involvement Post-Audit

### Protocol involvement post-audit

After the review window ends, the work shifts from discovery to remediation and verification. Sherlock’s goal in this phase is simple: deliver a clean set of validated findings, help your team remediate them efficiently, and verify fixes before release.

#### 1) Findings are finalized and validated

Sherlock reviews submissions and consolidates the output into an actionable issue set. This includes validation, deduplication, and severity calibration so the protocol team is not sorting through raw noise.

Sherlock prioritizes issues that change real security risk. High and medium severity findings receive the most attention because they are the most likely to lead to fund loss or material system compromise.

#### 2) Protocol reviews the final issue set

Once the protocol receives the final list, the team confirms disposition for each item:

* Will fix for the upcoming release, or
* Accepted risk (acknowledged without fixing), or
* Disputed / needs clarification where the team believes context changes impact.

There is no universal fixed deadline for this step. The practical requirement is responsiveness so remediation and verification can be scheduled without blocking a launch.

#### 3) Remediation and PR linking

For issues marked “will fix,” the protocol implements patches and links each fix to the corresponding finding (typically via separate PRs). This keeps the remediation record clean and makes fix verification faster and more reliable.

#### 4) Fix verification

Sherlock then reviews the patch set to confirm:

* the original issue is fully resolved,
* the fix matches intended behavior, and
* the change does not introduce new risk.

For staffed engagements, fix verification is performed by the assigned review team. For contest-based reviews, fix verification follows the same principle: reviewers verify the relevant patch set against the validated findings.

#### 5) Final report and release readiness

After fix verification completes, Sherlock provides the final report reflecting the validated issues, severity decisions, and verification status. This becomes the record for internal sign-off and release readiness.<br>

#### Follow-up review windows

Sometimes remediation materially changes the attack surface (large refactors, new modules, revised accounting, new integrations). When the patch set is too large to confidently verify in a short window, Sherlock may recommend a follow-up review focused on the changes before sign-off.
