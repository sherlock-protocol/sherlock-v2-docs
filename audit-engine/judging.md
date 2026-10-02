# Judging

Audit Engine judging moves fast so participants can improve reports while submissions are open. Preliminary AI judge feedback often arrives within minutes on submissions. Lead Judge rulings follow but can take longer and are not guaranteed to happen during the Submissions Window. Protocol teams can provide feedback and judgment updates during the engagement.

### Pipeline

Judging follows a staged pipeline:

1. **Sherlock AI judge**\
   Checks validity, severity, deduplication, known issue status, and in-scope status. Feedback is often available within minutes so participants can [Rewrite and Resubmit](for-participants.md#rewrite-and-resubmit) while submissions are open.
2. **Lead Judge**\
   Oversight and edits on AI judge judgments. Overturns wrong AI judgments, decides edge cases and keeps severity consistent across the engagement.
3. **Protocol team feedback and judgment updates**\
   Protocol teams can provide feedback and update judgments on findings during and after the Submissions Window.

When the engagement is finished, you'll see finalized curated **Findings** (including categories such as Invalid But Interesting), the downloadable **Audit Report**, and the [**Benchmarking**](benchmarking.md) report.

### Categories and severity

Findings are labeled with engagement severity levels (for example Critical, High, Medium, Low, Informational) plus labels such as **Invalid But Interesting** for the protocol team when a report is not a valid issue compared to the ruleset but still useful context. This issues may earn a Neutral judgment instead of Valid or Invalid.

Severity weights for payout scoring are configured per engagement. Confirm the weights published for your engagement.

### For participants

Treat the engagement / submissions period as the time to perfect reports:

* Watch preliminary AI judge feedback closely
* Use [Rewrite and Resubmit](for-participants.md#rewrite-and-resubmit) to improve clarity, exploit path, and severity justification
* Remember each [Rewrite and Resubmit](for-participants.md#rewrite-and-resubmit) adds **+0.5** to the [Issues Ratio](for-participants.md#issues-ratio) denominator but can change the issue's numerator from a **+1.0** (accepted) to a **0** (rejected)

### For protocol teams

* Preliminary AI judge feedback will happen within minutes, and Lead Judge review shortly thereafter. In default cases, issues are not shown to you until the Lead Judge has reviewed them.
* Provide feedback and judgment updates when you disagree with validity or severity
* Critical and High alerts (validated by the Lead Judge) trigger special notification via Slack / email
* Payouts follow the Accepted set and eligibility rules at the stated payout snapshot date

See also: [How Audit Engine Works](how-audit-engine-works.md), [For Protocol Teams](for-protocol-teams.md), [For Participants](for-participants.md), [Benchmarking](benchmarking.md).
