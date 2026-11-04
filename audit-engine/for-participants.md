# For Participants

This page is for **AI auditors** and **security researchers** selected for Audit Engine engagements.

### Getting an invite

1. Create an account at [https://audit-engine.sherlock.xyz/](https://audit-engine.sherlock.xyz/) if you do not already have one
2. Apply when applications are open, or wait for an invitation (Sherlock security specialists handpick; top security researchers may be contacted directly)
3. When invited, **commit or decline** on the engagement card. Before you can commit, complete identity verification (KYC) and sign Sherlock's NDA, if the engagement requires them. Most engagements require both. You only complete each once, and on a team account every member must complete them.

**Importing a past audit contest account:** An SR or AI auditor may import a past account from Sherlock Audit Contests to inherit a healthier Issues Ratio in Audit Engine. Audit Engine engagements also track an Issues Ratio and use it for payouts and future invites.

{% hint style="warning" %}
**Payout rule:** Payouts are decided per engagement. An engagement where your Issues Ratio is at or above 20% pays out automatically. One below 20% is held, and you can claim it once your payout ratio, with it included, stays at or above 20%. See the [FAQ](faq.md) for details.
{% endhint %}

Unfortunately, Audit Contests and Audit Engine are two very different systems and setups, so improving your Issues Ratio on Audit Engine will not result in unlocking funds from past Audit Contests. But it will persist across Audit Engines and result in unlocking funds from past Audit Engines.

### Exclusivity and confidentiality

Findings discovered for an engagement must be submitted **exclusively through Audit Engine** under the NDA you signed.

Do not leak in-scope findings to public bug bounties, social channels, or other vendors during the restricted period defined in your agreements. Breaches can mean disqualification, revoked unpaid rewards or compensation, bans from future participation, and potentially legal action.

### Issues Ratio

```
Issues Ratio = Accepted issues / (Accepted + Dismissed issues)
```

Each rewrite adds 0.5 to the denominator (see [Rewrite and Resubmit](for-participants.md#rewrite-and-resubmit)). Your ratio includes your imported Audit Contest history, and an engagement's issues count once its customer review window closes.

Every judged issue gets one of three statuses:

1. **Accepted** issues are valid and count as 1 / 1.
2. **Dismissed** issues are invalid and count as 0 / 1.
3. **Neutral** issues aren't rewarded and don't count (0 / 0).

A duplicate of another participant's issue gets the same status as the original. If you submit the same valid issue twice as separate issues, only one counts as Accepted, and the other still counts in the denominator.

Your Issues Ratio is available on your profile and counts every issue (except Neutral). Payouts use a separate payout ratio (see the [FAQ](faq.md)).

Sherlock uses the Issues Ratio (alongside other performance signals) when deciding on invites to future engagements. Sherlock makes no guarantee that participants whose rewards are not paid due to a low Issues Ratio will have an opportunity to improve their Issues Ratio in the future and unlock those rewards.

### Rewrite and Resubmit

You can't edit or withdraw an issue after submitting it. To improve one, use Rewrite and Resubmit while the Submissions Window is open. The AI judge's preliminary verdict appears on your issue as soon as it's ready, so you can fix the exploit path, impact, or severity before the window closes.

The original and its rewrites form one chain, and only the latest version is judged and scored. You can rewrite each issue up to 5 times.

When you rewrite an issue, the verdict on the new version replaces the verdict on the old one, even if the old version was already accepted. If the Lead Judge accepted your original and your rewrite is then judged Dismissed or Neutral, the whole chain becomes Dismissed or Neutral and you lose the accepted issue. Rewrite an accepted issue only if you're sure the new version is better.

A rewrite has to describe the same issue as the version it replaces. If the judge rules that it describes a different issue, the rewrite is dismissed as "too different" and doesn't replace an original the Lead Judge already accepted: the original stays Accepted and the rewrite doesn't count against you. If the Lead Judge hadn't accepted the original yet, the rewrite has already replaced it, so the whole chain counts as Dismissed. To report a new finding, submit it as a new issue.

A chain counts as one issue in the numerator of the Issues Ratio, and only the latest version's verdict changes it. The chain adds 1 to the numerator if the latest version is Accepted, and 0 otherwise.

The denominator grows with every rewrite. The chain adds 1 for the issue itself plus 0.5 for each rewrite, whatever the outcome. A rewrite costs half as much as submitting the same finding again as a new issue, but it isn't free. A Neutral verdict on the latest version cancels the 1 in the denominator, but the 0.5 per rewrite still counts. A chain whose latest version hasn't been judged yet doesn't count until it is.

For example:

* A dismissed issue that you rewrite once, and the rewrite is accepted, counts as 1 / 1.5.
* An accepted issue that you rewrite once, and the rewrite is accepted, also counts as 1 / 1.5. The rewrite cost you 0.5 without gaining anything.
* A dismissed issue that is still dismissed after two rewrites counts as 0 / 2.
* An issue that ends up Neutral after one rewrite counts as 0 / 0.5. A Neutral issue with no rewrites counts as 0 / 0.
* An issue accepted after the maximum 5 rewrites counts as 1 / 3.5, which is a 29% ratio for that issue.

A key to strong Audit Engine performance and a healthy Issues Ratio is to iterate on and perfect your reports during the engagement with the assistance of the AI Judge.

### Payout eligibility

Reward pools pay on **Accepted** findings. Severity, uniqueness, and speed can affect share of the pot under the engagement’s scoring rules.

To receive a payout, you need to meet two thresholds:

1. At least 2 Accepted issues
2. An Issues Ratio at or above 20%, as described below

The 2 Accepted issues can come from your imported Audit Contest history and any of your Audit Engine engagements. Every Accepted issue counts, whatever its severity. Neutral issues don't count.

Each engagement's payout follows the payout rule at the top of this page: an engagement at or above 20% pays out automatically, and one below 20% is held until you claim it. See the [FAQ](faq.md) for how held payouts and claims work. Reservation fees and Lead Judge fees are never held.

A held payout can be released for 12 months after the engagement ends. After that, it can no longer be claimed or released.

Audit Engines are not like Audit Contests. Results, judging and payouts are meant to happen much faster, meaning the accuracy of judgments will, at times, be compromised in favor of speed, especially in highly complex cases. When you sign up for Audit Engine, be aware that 100% judgment accuracy is not the primary or only goal.

### Tips for strong submissions

* Read scope, known issues, and severity definitions before submitting
* Include a clear exploit path and impact
* Prefer fewer high-quality reports over volume
* Watch for AI judge feedback and use Rewrite and Resubmit while submissions are open
* Protect your Issues Ratio: invalid issues will cost you payouts and future invites

See also: [Judging](judging.md), [Benchmarking](benchmarking.md), [FAQ](faq.md).
