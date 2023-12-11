# The Lead Judge's Role

### Lead Judge Fixed Pay

\
Apart from the USDC earned from the contest pool, where judges compete with each other, the Lead Judge can also receive fixed compensation according to the following breakdown:

* 50% guaranteed payment
* 25% based on the duration taken for completion
  * Full 25% if finished within 28 days after the audit contest's end date.
  * 18.75% if finished within 35 days after the audit contest's end date.
  * 12.5% if finished within 42 days after the audit contest's end date.
  * 0% If finished after 42 days
* 25% based on the outcome of escalations
  * First, calculate the escalation factor: number of issues that undergo a change in state(severity or duplication) due to escalations divided by the total number of issues. _(2/100 = 0.02)_
  * Multiply by 20  _(0.02 \* 20 = 0.4)_&#x20;
  * Subtract from maximum amount _((1-0.4) \* 25% = 15%)_

### Lead Judge responsibilities

* Judge issues to the best of their abilities in a fair manner.
* Lead the judging through all the phases and achieve the two-week timeline goal to announce initial results.
* Must communicate effectively with all parties involved
* Must add relevant comments if required on valid/invalid issues to make the process easier for everyone involved.

Additional Note: The Lead Judge **must allocate sufficient time after the contest to judge & take it through to the final state**. Hence please understand the role & commitment to take up the Lead Judge opportunities wisely based on your availability.

### Phase 1:

* The Lead Judge takes part in the judging contest.
* If the predicted time for a judging contest is too short, the Lead Judge can ask Sherlock to lengthen it by up to 3 days. This needs to be communicated with Sherlock at least 24h before the initial judging contest end time.
* At the end of the contest, the Lead Judge's final judging repository will be synced to the original contest judging repository to generate the issues.
* Make sure you consider borderline issues during the contest. Read more [https://docs.sherlock.xyz/audits/judging/guide-to-judging-contests#you-must-clear-3-thresholds-to-be-eligible-for-usdc](https://docs.sherlock.xyz/audits/judging/guide-to-judging-contests#you-must-clear-3-thresholds-to-be-eligible-for-usdc)

### Phase 2:

* The judge receives a report, containing potential misjudged issues. This report is based on the submissions from other judging contest participants and their reputation.&#x20;
* The initial list of issues will then be shared with the protocol team to add comments and relevant labels.
* The Lead Judge shall coordinate with the protocol team, Lead Senior Watson & Sherlock to resolve the issues based on the comments/labels. You can also add comments on the issues to help with the process.
* These are the **actions** the Lead Judge is **allowed** to do during this phase:&#x20;
  * &#x20;**Validity related**: In the case of `Sponsor disputed` issues, the Lead Judge must **close the issue** if you **agree** with the Sponsor's comment, or **keep it open** as is if you **disagree** with the Sponsor's comment. In both cases, relevant comments must be added.&#x20;
  *   **Severity related**: In case of valid issues with `Sponsor confirmed`, but `Disagree with Severity` issues, if you agree with the Sponsor's argument for downgrading/upgrading the issue severity, please change the respective labels:

      * If the final state of the issue should be a `Medium/High` Please remove the old severity label, remove `Disagree with severity` label and **add the new severity label**.&#x20;
      * If the final state of the issue should be a `low` then please **remove** the previous severity label and **close the issue.**

      In case you disagree with the Sponsor's comment on the issue's severity, please **keep it as is** and add relevant comments to it.&#x20;
  * **Duplication related:** If the Sponsor disagrees with the duplication, please change the duplication accordingly if you agree based on [#duplication-instructions](the-lead-judges-role.md#duplication-instructions "mention").  \
    In case you disagree you can add the relevant comment and keep the issue **as is**.
  * The final list of **open** issues must only have valid issues that are to be rewarded.&#x20;

The ideal timeline to complete the 2 phases is **two weeks** from the end of the contest. Initial results must be announced within this period.

### Phase 3:

* Initial results will be generated & announced based on the final issue state from Phase 2. Completion of this step opens up the Escalation period.
* The Lead Judge comments on every escalation within 48 hours after the escalation period ends. The Lead Judge facilitates the discussion between parties to achieve consensus on the technical impact of the issue, leaving the severity judgement to Sherlock. The Lead Judge is available to answer questions at any time before the final announcement is made.
* During this phase, the Lead Judge must only **comment** on escalations and suggest necessary actions to be taken by Sherlock. Please **do not** open/close issues and **do not** change severity labels in this phase.&#x20;
* Sherlock will make necessary changes to the issues, resolve the escalations, and announce the final results.

### Duplication Instructions:

*   The main issue is to be kept **open** and must have `Has Duplicates` label.  \
    [Main issue example](https://github.com/sherlock-audit/2023-02-olympus-judging/issues/49)\


    <figure><img src="../../.gitbook/assets/Screenshot 2023-05-31 at 12.12.10 PM.png" alt=""><figcaption></figcaption></figure>
*   The duplicate issues must be **closed**, have a `Duplicate` label, and **should have a "Duplicate of ##" in the body of the issue at the end.** Please refer image below. \
    [Duplicate issue example](https://github.com/sherlock-audit/2023-02-olympus-judging/issues/49)\


    <figure><img src="../../.gitbook/assets/Screenshot 2023-05-31 at 12.14.42 PM.png" alt=""><figcaption></figcaption></figure>

#### The Best Lead Judge

* Understands Sherlock's Judging guidelines
* Understands the contest codebase well
* Judging effectively results in ideally zero valid escalations.
* When closing an open issue adds relevant comment for context.
