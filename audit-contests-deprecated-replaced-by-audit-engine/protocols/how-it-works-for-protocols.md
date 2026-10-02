---
description: >-
  What a Sherlock audit contest is, how the process works (scoping, contest
  window, live judging, remediation, and fix verification), and how to plan
  timelines for a mainnet launch or upgrade.
---

# How Audit Contests Work

### How Audit Contests Work

Sherlock audit contests are time-boxed public review programs that bring many independent researchers onto the same scope under clear rules and incentives. The goal is high-throughput discovery, paired with structured judging and fix verification so teams can ship against a clean set of findings.

Audit contests are commonly used for first-time mainnet launches, major upgrades, new deployments, and high-impact integrations.

<figure><img src="../../.gitbook/assets/Screenshot 2026-01-28 at 3.56.05 PM.png" alt=""><figcaption></figcaption></figure>



#### The Audit Contest Process

**1) Request + scoping**

Submit an intake request. We’ll confirm scope, risk areas, constraints, and target dates. For most scopes, Sherlock can begin within a few days once scope and logistics are finalized.

**2) Quote + scheduling**

Sherlock provides a quote based on scope complexity and the review window. Once scheduled, your team reserves the slot with a deposit.

**3) Finalizing the scope**

Before the contest begins, you provide the final commit / branch and any required materials (deployment context, docs, testing guidance, known assumptions). This is the baseline the contest is judged against.

**4) Contest window**

During the contest, vetted researchers review the scope in parallel and submit issues. Your team should be available to answer clarifying questions in the shared channel.

**5) Live judging + severity calibration**

Submissions are reviewed as they come in. Sherlock judges validate issues, deduplicate similar reports, and calibrate severity so the final output is actionable. At the end of judging, you receive a curated list of confirmed findings with consistent severity and remediation guidance.

**6) Acknowledgement + remediation plan**

Your team acknowledges findings and indicates which ones will be addressed for the upcoming release. At this point, you also schedule fix verification.

**7) Fix verification**

You ship fixes as PRs and provide the new commit for review. Sherlock verifies that fixes resolve the issue and don’t introduce new risk. If the change set is large, Sherlock may recommend a short follow-up review window to re-check the updated surface area.

**8) Final report**

You receive a final report that includes the validated findings, severity decisions, and fix verification status — a clean paper trail your team can launch against.



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
**Fix review:** This will be done by the Lead Senior Watson if it can be accomplished in 1 day or less. If not, Sherlock suggests a small follow-up audit contest. Could take as little as 1 day, or it could take 1-2 weeks to schedule and complete (depending on number of issues and Lead Senior Watson availability, etc.)\
\
**Generally, Sherlock recommends a protocol team not expect to deploy/launch their protocol until 2-3 weeks after the audit contest finishes. However, if not issues are found, a protocol team could launch as soon as 3 days after the audit contest ends.**&#x20;
{% endhint %}
