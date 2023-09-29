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
* 25% based on the number of accepted escalations
  * First, calculate escalation factor: number of accepted escalations (max 1 per issue) divided by total number of issues. _(2/100 = 0.02)_
  * Multiply by 20  _(0.02 \* 20 = 0.4)_&#x20;
  * Subtract from maximum amount _((1-0.4) \* 25% = 15%)_

### Lead Judge responsibilities

* Judge issues to the best of their abilities in a fair manner.
* Lead the judging through all the phases and achieve the two-week timeline goal to announce initial results.
* Must communicate effectively with all parties involved
* Must add relevant comments if required on valid/invalid issues to make the process easier for everyone involved.

Additional Note: The Lead Judge **must allocate sufficient time after the contest to judge & take it through to the final state**. Hence please understand the role & commitment to take up the Lead judge opportunities wisely based on your availability.

### Phase 1:

* The Lead Judge takes part in the judging contest.
* At the end of the contest, the Lead Judge's final judging repository will be synced to the original contest judging repository to generate the issues.
* Make sure you consider borderline issues during the contest. Read more [https://docs.sherlock.xyz/audits/judging/guide-to-judging-contests#you-must-clear-3-thresholds-to-be-eligible-for-usdc](https://docs.sherlock.xyz/audits/judging/guide-to-judging-contests#you-must-clear-3-thresholds-to-be-eligible-for-usdc)

### Phase 2:

* The judge receives a report, containing potential misjudged issues. This report is based on the submissions from other judging contest participants and their reputation.&#x20;
* The initial list of issues will then be shared with the protocol team to add comments and relevant labels.
* The Lead Judge shall coordinate with the protocol team, Lead Senior Watson & Sherlock to resolve the issues based on the comments/labels. You can also add comments on the issues to help with the process.

The ideal timeline to complete the 2 phases is **two weeks** from the end of the contest. Initial results must be announced within this period.

### Phase 3:

* Initial results will be generated & announced based on the final issue state from Phase 2. Completion of this step opens up the Escalation period.
* The lead judge comments on every escalation within 48 hours after the escalation period ends. The lead judge is available to answer questions at any time before the final announcement is made.
* Sherlock resolves the escalations & Final results are announced.

### Duplication Instructions:

*   The main issue is to be kept **open** and must have `Has Duplicates` label.  \
    [Main issue example](https://github.com/sherlock-audit/2023-02-olympus-judging/issues/49)\


    <figure><img src="../../.gitbook/assets/Screenshot 2023-05-31 at 12.12.10 PM.png" alt=""><figcaption></figcaption></figure>
*   The duplicate issues must be closed, have a `Duplicate` label, and **should have a "Duplicate of ##" in the body of the issue at the end.** Please refer image below. \
    [Duplicate issue example](https://github.com/sherlock-audit/2023-02-olympus-judging/issues/49)\


    <figure><img src="../../.gitbook/assets/Screenshot 2023-05-31 at 12.14.42 PM.png" alt=""><figcaption></figcaption></figure>

#### The Best Lead Judge

* Understands Sherlock's Judging guidelines
* Understands the contest codebase well
* Judging effectively results in ideally zero valid escalations.
* When closing an open issue adds relevant comment for context.
