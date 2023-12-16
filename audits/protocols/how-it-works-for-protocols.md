# How it Works for Protocols

Whether this is your protocol’s first audit before launching on mainnet, or latest version, Sherlock’s audit experience is designed to provide the familiarity of a traditional audit, with drastically better results.

**A protocol’s audit process:**

<figure><img src="https://lh7-us.googleusercontent.com/VL9KNryxABlPhwON2oxTILCjtSDAQ28RlyortR0kHbfknMe2JKAq8O2WrDi4CArHmZLU_aEqM1TGb2mCmgUscMd_MaWOWaHNmgtXYPR2TzTfPuBTm2ehUkh2AmMFfaArPbmV95iaRkU7Gzl6LJBNwmY" alt=""><figcaption><p>The timeline for a Sherlock audit</p></figcaption></figure>

1. You can request an audit [here](https://audits.sherlock.xyz/request-audit). Sherlock can usually start an audit within 3 days.&#x20;
2. Sherlock will contact you to discuss your audit scope, expected timeline, and requirements to get an audit started (check out Sherlock's [Audit Requirements Checklist](https://docs.google.com/document/d/10\_t7Kt814Otp-FMFK8mvCsxb3tX3wyu1Z9V4nhZxTY8/edit?usp=sharing) for items Sherlock requires to start an audit).
3. Sherlock conducts an initial assessment and provides you with a quote based on the length of time required for the audit.
4. You then reserve your audit slot by putting down a refundable deposit for 25% of the cost of the audit.
5. Three days before the audit starts, you send Sherlock the final commit, branch, contracts, and the remaining portion of the audit deposit.
6. Once the audit contest portion of the audit begins, Sherlock will ask your team to be available to answer questions from security experts (mostly in a Discord channel).&#x20;
7. Immediately after the audit contest ends, the judging contest starts. The judging contest will last a variable number of days, depending on the number of issues submitted. After the judging contest ends, Sherlock will provide you with a curated, de-duplicated list of all High and Medium-severity findings.
8. You then have 72 hours to acknowledge and indicate which submitted issues you intend to fix and schedule a fix review to be completed within 3 weeks.
9. Sherlock asks that you implement any fixes (a separate PR for each issue being fixed) and deliver the new commit hash to Sherlock 24 hours before your fix review starts. We also ask that you comment on each open issue (in the Sherlock repo) with a link to the PR that fixes that issue.&#x20;
10. Around the same time as Step #9, Sherlock runs an "Escalation Period" where security experts can stake USDC and flag any issues that they think were not categorized correctly for a second opinion.&#x20;
11. Post-fix review, you will receive sign-off to launch on mainnet and a final report, which gives you the option to add coverage at any point in the future.
12. Sherlock works with you to get your coverage and bug bounty live (if you decide you want smart contract exploit coverage).

{% hint style="warning" %}
**Important timeline considerations**\
\
The length of the audit contest itself will be communicated to the protocol team as part of the initial quote/scoping. However, the post-contest process can take a couple days, or it can take a few weeks, depending on the number of issues found:\
\
**Audit Contest:** Communicated in the quote/scoping\
**Judging Contest:** Variable number of days immediately after audit contest\
**Issue Verification:** Depends on the number of issues submitted, but could take 1 day or could take 7 days (also depends on the productivity of the protocol team)\
**Issues fixes:** Depends on the number of valid issues, but could take 1 day or could take 1-2 weeks (also depends on the productivity of the protocol team)\
**Escalation Period:** Once the issues have been verified, this is a "double-checking" process that takes 48-72 hours in total and usually occurs while the protocol team is fixing issues.\
**Fix review:** This will be done by the Lead Senior Watson if it can be accomplished in 0.5 days. If not, Sherlock suggests a small follow-up audit contest. Could take as little as 1 day, or it could take 1-2 weeks to schedule and complete (depending on number of issues and Lead Senior Watson availability, etc.)\
\
**Generally, Sherlock recommends a protocol team not expect to deploy/launch their protocol until 2-3 weeks after the audit contest finishes. However, if not issues are found, a protocol team could launch as soon as 3 days after the audit contest ends.**&#x20;
{% endhint %}
