# The Lead Judge's Role

### Lead Judge Fixed Pay

\
Apart from the USDC earned from the contest pool, where judges compete with each other, the Lead Judge also receives fixed compensation according to the following breakdown:

* 110% base payment
* Up to 10% subjective helpfulness score. Achieved by being helpful to the Sherlock Judge during the escalation resolution stage. It's a subjective metric.
* A penalty of a minimum of 5% and (num_issues / 300) * 5% per every day of delay beyond the unpenalized judging days' time.
  * The unpenalized judging time is 48 hours plus 24 hours for every 150 issues submitted in a contest. For example, if there are 100 issues submitted, then the unpenalized judging time is 48 + 24 * 100/150 = 64 hours.
* A penalty of 10 times the accepted escalation ratio
  * The accepted escalation ratio is the ratio of the accepted escalations (equal to the number of changes that the preliminary results need to undergo) to the number of all issues. For example, if there are 200 submissions and 2 escalations are accepted, the escalation ratio is 2/200 = 1%, and this will result in a 10% penalty.

Simply put, we expect the judging (including the judging contest) of a 300-issue contest to be completed within 8-10 days with a minimal number of accepted escalations. If there were 300 issues, the Judging contest took 4 days, followed by 4 days of preliminary judging without a penalty. If the preliminary judging took 6 days in total, it would amount to (6 - 4) * 5% = 10% time penalty. Then, 3 escalations were accepted, but the highest mark possible was chosen for the escalation usefulness – 10%. This means that the final multiplier is 110% + 10% - (6 - 4) * 5% - 10 * 3 / 300 = 110% + 10% - 10% - 10% = 100%. The Lead Judge receives their base pay and their contest points remain unaltered.

The above multiplier scales not only the USDC payout but also the number of Judging (leaderboard) Points received by the Lead Judge from the contest. If the multiplier is below 0, the USDC Payout is capped at $0, but the Judging Points for the contest are assumed to be the Lead Judge's ranking points multiplied by the multiplier (negative). So, for example, if a Lead Judge had 500 Leaderboard points at the time of the contest and gets a -20% multiplier, they get a $0 payout and a -100 points contest result.

Sherlock reserves the right to alter the above formulas or inputted values in rare cases, especially in those when the complexity, number, or accuracy of issues is unusual.

An example of the calculated multiplier can be seen in [this spreadsheet](https://docs.google.com/spreadsheets/d/1kuiDbXKl7VjOVQZvqMmj9wHLV73Vj2fMulXiRKFr6H0/edit?usp=sharing).

### Lead Judge responsibilities

* Judge issues to the best of their abilities in a fair manner.
* Lead the judging through all the phases and achieve the best possible timeline goal to announce preliminary results.
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

The ideal timeline to complete the 2 phases is about **two weeks** from the end of the audit contest.

### Phase 3:

* Preliminary results will be generated & announced based on the final issue state from Phase 2. Completion of this step opens up the Escalation period.
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
