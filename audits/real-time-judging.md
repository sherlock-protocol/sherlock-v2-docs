---
description: Documentation about real-time judging
---

# 🧑‍⚖️ Real-Time Judging

## Participating in Real-Time Judging

You’re going to review some issues anyway, why not get paid for it?

### What’s in it for me?

Roughly 8% of the value of the audit contest pot will be set aside as rewards for judges. If an audit has a $50,000 pot, then the portion of the judging pot that will be publicly available is \~$4,000.

There’s no requirement to judge all of the issues submitted in a contest. If you judge 1 very difficult issue correctly, you could technically earn the majority of the judging pot.

### How can I become a Judge?

If you submit at least 1 valid issue in a Sherlock contest, you are eligible to participate in judging.&#x20;

Watsons that were on the audit or legacy judging leaderboard at the time of announcement will start with an initial signal score.&#x20;

### What is Real-Time Judging?

Real-Time Judging is a live judging contest where hundreds of Judges can contribute to judging contest issues at the same time. Normally \~8% of the audit contest pot is allocated to the judging pot. You can earn USDC by judging just one issue!

You’ll be able to track every issue’s severity and duplication progress in the Overview page. You’ll also be able to see each issue’s severity and duplication status. This page will constantly update to show the latest votes of every Watson.&#x20;

![](https://lh7-rt.googleusercontent.com/docsz/AD\_4nXfxORK3RQQV9cts-KCLL3Kzwf7XlX2Xn4s7vFXqbeGvglGHrJxaV5ASGuQvSf5hJncNHC5LIlfHf\_g3xMhzi0NzaEqucg3y04Sweeb8LbUIPvY5vLIDwFn0pfhEh3LZBsPPFfOYc7wvcaEIszqJzaMgpDoZ?key=vBHXKQdJakMdc1gIGcMF8w)

If you want to participate, you can click on any issue to view the issue description, vote on the duplication status and choose the severity (High, Medium, Invalid).

![](https://lh7-rt.googleusercontent.com/docsz/AD\_4nXfunEKJYB2KkuBoI9mll1dGqcGBLsFS5wiviNgeB-yLLW4Q4KXbCKOfNftSk\_JUCtw6gcKX5Xjf-3KDOxswdZvjCrdfanRdxoDhTPjO0KUezkEzhr0cBkr7aPT2Ql17G2qQVj8r4JICnL76CTg\_UrYS3Nyw?key=vBHXKQdJakMdc1gIGcMF8w)\
\


### Real-Time Judging Timeline

Judging goes live right after the audit contest ends. You can find it in the [Contests](https://audits.sherlock.xyz/contests) section of the Sherlock app. It will be available for any contest in the “Judging” stage.&#x20;

Each issue must hit 100% on the Severity and Duplication Progress to be in the “Finalizable” state. When every issue reaches this state, the contest judging progress will reach 100% and the preliminary results can be viewed. Voting is still live during this phase.

After 24 hours the voting will end and the final results will be announced.

### Key Features of Real-Time Judging

* You can judge only a subset of the issues and still get paid for it (even just 1 issue!)
* The votes and comments of other judges update in real-time
* The currency of the system is called “signal” and you gain signal for correct judgments and lose signal for incorrect judgments
* The reward for judging an issue increases over time
* The reward for voting on an outcome (i.e. Medium) decreases after others vote for the same outcome
* There is no escalation period, the Sherlock Judge has discretion to review controversial issues
* As issues become more controversial (i.e. lots of votes on Medium AND invalid) the signal required to finalize that issue’s outcome increases
* Judging contests are finalized once there is enough signal voting in the same direction on each issue
* Once all issues are in a finalized state, there’s a 24-hour period for more voting to occur, and then the contest results become final
* There is no fixed timeframe for a judging contest, it could finalize in 3 days and payouts could happen the day after

> Important! Once you vote or write a comment, you cannot change it. Think carefully before taking any action and include as much relevant detail in your comments as possible.&#x20;

### What is Signal?

Signal is the currency of Real-Time Judging.&#x20;

Every Judge starts with Signal. Signal is the weight that your vote is assigned. The more Signal you have, the more you can influence the judging results and the more rewards you earn for valid votes.

### How can I increase my signal?

After an audit contest, your Signal increases for correct judgments and decreases for incorrect judgments. You can increase your Signal in two ways:

1. Submit correct judgments
2. If your Signal is <100, you can increase your Signal to a maximum of 100 by submitting valid issues in an audit contest

If your Signal gets to 0, you can no longer participate in Real-Time Judging. The maximum possible Signal is 1,000.

### &#x20;How is Signal calculated?

For a technical calculation of Signal, see [this spreadsheet](https://docs.google.com/spreadsheets/d/1fQ-8HS4SL0sXqKg6bHHlHFFhbj8Y14cqWOiupYIpIrQ/edit?usp=sharing).

To initialize the system, every Watson’s signal was calculated based on their audit and judging leaderboard positions. See [this spreadsheet](https://docs.google.com/spreadsheets/d/1fQ-8HS4SL0sXqKg6bHHlHFFhbj8Y14cqWOiupYIpIrQ/edit?usp=sharing).&#x20;

### How do I earn USDC?

You can see the reward and penalty for every action you take on an Issue page. And at the bottom of the Issue page, you can see the aggregate max rewards and aggregate max penalty for your submission.&#x20;

The rewards earned for voting increase your signal score, and the penalties decrease it. The larger your signal score, the larger the rewards you earn for voting correctly. However, the penalty for incorrect votes will also be larger.&#x20;

Your USDC payout is calculated by subtracting your earned penalties from your earned rewards. The judging pool is shared proportionally with the Judges who have positive points.

Example

* Alice earned a reward of 25 for correctly voting High on issue #1
* Alice earned a penalty of 10 for incorrectly voting Invalid on issue #2
* Bob earned a reward of 5 for correctly voting High on issue #1
* Alice ends up with 15 points (25 - 10)
* Bob ends up with 5 points
* Alice will take 75% of the judging pot (15/20)
* Bob will take 25% of the judging pot (5/20)

### How are rewards and penalties calculated?

AMM (Automated Market Maker) logic decides the rewards and penalties for each vote based on Signal that has already been voted on that judgment.&#x20;

The AMM logic allows for a fair distribution of rewards while mitigating sybil and collusion attacks.

More details will be added to this section later.&#x20;

### &#x20;How does commenting work?

Every severity and duplication judgment on every issue requires a comment. If someone has commented on that same judgment before you (and you agree with it), you can vote for their comment instead of writing your own.&#x20;

Writing a comment can earn you a 300% reward boost on that judgment if your comment accrues the most Signal, but it can result in a 10% penalty if it doesn’t accrue the most Signal.&#x20;

You are only able to write 1 comment per severity and duplication judgment. And you are not allowed to edit your comment. So only write a comment once you feel you have a strong grasp of the issue, and include as much relevant detail in your comment as possible.&#x20;

### How can I escalate my issue if I disagree with the outcome?

Escalations have been deprecated. Instead, the same mechanism naturally occurs in Real-Time Judging if there is a material amount of Signal voting on different outcomes (i.e. Medium vs. Invalid).

Every issue with a high degree of controversy will attract the attention of the Sherlock Judge, who has the final say on every judgment.&#x20;

In the previous system, the ability to escalate an issue was earned by doing well in the judging contest and submitting valid issues. In the same way, you can increase your Signal by judging well and submitting valid issues in audit contests.&#x20;

### How does Real-Time Judging work in private audit contests?

Only the participants in the private audit contest can participate in Real-Time Judging. The threshold to finalize issue judgment will necessarily be lower in these contests.

### What if I submit spam issues in the audit contest so I can earn rewards for them in the judging contest?

If a Watson does not meet the Payout Threshold after any audit contest, the issues they submitted in the audit contest will not count for judging rewards.&#x20;

\
\
\
\
