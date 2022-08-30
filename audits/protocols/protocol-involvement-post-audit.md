# Protocol Involvement Post-Audit

Once an audit is complete, Sherlock saves protocols days of work by utilizing its own in-house team to begin the evaluation process. The post-audit track takes the following path:

1. Sherlock will review all issues, de-duplicate submissions, and judge every issue.
   * Sherlock is focused exclusively on high and medium severity findings, as these are the types of vulnerabilities which will cause a loss of user funds and most materially damage the reputation protocols.
2. Protocol team will receive a final list of vulnerabilities, and then has 72 hours to indicate which issues they intend to fix and acknowledge which issues aren’t relevant vulnerabilities given their protocol design.
3. The protocol team will then have up to 3 weeks to schedule and complete a fix-review, where Sherlock’s Lead Senior Watson (at minimum) will conduct a <0.5 days audit to make sure the fixes have been implemented correctly and haven’t introduced vulnerabilities.

> Note: If a protocol fails to deliver a new commit hash and separate PRs for each issue within 3 weeks, then Sherlock can no longer guarantee that a fix review will be scheduled, disqualifying a protocol from implementing smart contract exploit coverage at go-live. For transparency, Sherlock puts a 3-week timeline on this fix review requirement out of best-practices, since the quality of a fix review is only as good as the senior engineer’s ability to maintain context of the entire code base into perpetuity. Given every person’s natural limitations to remember everything forever, Sherlock believes that the fix reviews must be completed in a reasonable timeframe in order to have a high-quality fix review conducted.

4\. Once a fix-review is completed, the senior engineer will verify that the protocol is good to launch on mainnet with the final commit. At this point, a protocol is fully qualified for smart contract exploit coverage, which can be activated at any point in the future on the previously audited commit hash. A protocol will also receive a final audit report shortly thereafter.

> Note: If the senior auditor believes there are a material amount of changes required post-audit which can’t be reviewed in <0.5 days, Sherlock may require a smaller follow-up audit (see Audit Pricing and Timeline section) be conducted in order to qualify for coverage.
