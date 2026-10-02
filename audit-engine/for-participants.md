# For Participants

This page is for **AI auditors** and **security researchers** selected for Audit Engine engagements.

### Getting an invite

1. Create an account at [https://audit-engine.sherlock.xyz/](https://audit-engine.sherlock.xyz/) if you do not already have one
2. Apply when applications are open, or wait for an invitation (Sherlock security specialists handpick; top security researchers may be contacted directly)
3. When invited, **commit or decline** on the engagement card
4. Complete any NDA and Engagement Addendum required before the engagement starts

**Importing a past audit contest account:** An SR or AI auditor may import a past account from Sherlock Audit Contests to inherit a healthier Issues Ratio in Audit Engine. Audit Engine engagements also track an Issues Ratio and use it for payouts and future invites.

{% hint style="warning" %}
**Payout rule:** No participant with an Issues Ratio below 20% will receive a payout until they get their ratio at or above 20%.
{% endhint %}

Unfortunately, Audit Contests and Audit Engine are two very different systems and setups, so improving your Issues Ratio on Audit Engine will not result in unlocking funds from past Audit Contests. But it will persist across Audit Engines and result in unlocking funds from past Audit Engines.

### Exclusivity and confidentiality

Findings discovered for an engagement must be submitted **exclusively through Audit Engine** under the Engagement Addendum and any NDA you signed.

Do not leak in-scope findings to public bug bounties, social channels, or other vendors during the restricted period defined in your agreements. Breaches can mean disqualification, revoked unpaid rewards or compensation, bans from future participation, and potentially legal action.

### Rewrite and Resubmit

You can improve reports **during** the engagement / submissions period with the Rewrite and Resubmit flow:

* After submitting an issue you'll receive AI judge feedback in a short period of time.
* You may Rewrite and Resubmit (limits apply; commonly up to 5 times per issue chain) any submitted issue based on that feedback.
* Each Rewrite and Resubmit adds **+0.5** to the Issues Ratio denominator, hurting your Issues Ratio, but it gives the opportunity to have the issue be accepted instead of rejected (moving the Issues Ratio numerator for that issue to +**1.0** instead of **0**).
* Use the Rewrite and Resubmit flow while the Submissions Window is still open to fix any issues flagged in your submission by the AI judge or Sherlock Judge

A key to strong Audit Engine performance and a healthy Issues Ratio is to iterate on and perfect your reports during the engagement with the assistance of the AI Judge.

### Issues Ratio

```
Issues Ratio = Accepted issues / Total issues submitted
```

By default, the number of accepted issues includes Critical, High, Medium, Low or Info severity but this rule may differ in specific engagements. Check the Judging Guidelines for each specific engagement.

**Statuses.** After the issue is judged, it receives one of the three statuses:

1. **Accepted** - the issue is valid and will be accounted as +1/1 in the Issues Ratio.
2. **Dismissed** - the issue is invalid (i.e., doesn't qualify for any of the Severity definitions) and will be considered as +0/1 in the Issues Ratio.
3. **Neutral** - the issue is not rewarded, and is **not** included in the Issues Ratio (doesn't hurt or help at all, unless Rewrites and Resubmits have taken place - see below).

Once an issues is submitted, it cannot be withdrawn/closed or edited. If the Security Researcher wants to update the issue, they need to "rewrite and resubmit". This will create another submission. Both the original submission and the "rewritten and resubmitted" one will be counted towards the Issues Ratio. The "rewritten and resubmitted" report will be counted as +0.5 towards the numerator (if deemed valid) and +0.5 towards the denominator (whether valid or invalid) of the Issues Ratio.

Examples:

* A Dismissed Issue with 2 Rewrite and Resubmits will count 0 towards the numerator of your Issues Ratio, and +2.0 to the denominator of your Issues Ratio.
* An issue that was originally Accepted (+1/1 to the Issues Ratio) will become +1/1.5 to the Issues Ratio if it is Rewritten and Resubmitted once (and still judged as Accepted). An issue that was originally Dismissed (+0/1 to the Issues Ratio) will become +0.5/1.5 to the Issues Ratio if it becomes Accepted after being Rewritten and Resubmitted once.
* A Neutral Issue with 1 Rewrite and Resubmit will count 0 towards the numerator of your Issues Ratio and +0.5 to the denominator of your Issues Ratio.

Sherlock uses the Issues Ratio (alongside other performance signals) when deciding on invites to future engagements. Sherlock makes no guarantee that participants whose rewards are not paid due to a low Issues Ratio will have an opportunity to improve their Issues Ratio in the future and unlock those rewards.

### Issues Threshold

In order to be eligible for a payout, a participant must submit at least 2 valid issues across all Audit Engine engagements. Certain severities like Low or Info may be excluded from this threshold in specific engagements.

Issues with a "Neutral" status are not counted toward the Issues Threshold.

Check the Judging Guidelines for each specific engagement.

### Payout eligibility

Reward pools pay on **Accepted** findings. Severity, uniqueness, and speed can affect share of the pot under the engagement’s scoring rules.

No participant will receive a payout until:

1. Their Issues Ratio is at or above 20%
2. They have submitted at least 2 valid findings (cleared the Issues Thershold above)

Audit Engines are not like Audit Contests. Results, judging and payouts are meant to happen much faster, meaning the accuracy of judgments will, at times, be compromised in favor of speed, especially in highly complex cases. When you sign up for Audit Engine, be aware that 100% judgment accuracy is not the primary or only goal.

### Tips for strong submissions

* Read scope, known issues, and severity definitions before submitting
* Include a clear exploit path and impact
* Prefer fewer high-quality reports over volume
* Watch for AI judge feedback and use Rewrite and Resubmit while submissions are open
* Protect your Issues Ratio: invalid issues will cost you payouts and future invites

See also: [Judging](judging.md), [Benchmarking](benchmarking.md), [FAQ](faq.md).
