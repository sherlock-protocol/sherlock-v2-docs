---
description: Escalating an issue that you think was judged incorrectly
---

# Escalation Period



{% hint style="info" %}
For instructions on how to escalate an issue, please see[#how-do-i-escalate-an-issue](escalation-period.md#how-do-i-escalate-an-issue "mention")
{% endhint %}

### Summary

As a Watson, if you participate in an audit contest, submit issues and then think your issues (or others' issues) were not properly judged, you can escalate the issue and it will get further consideration.&#x20;

### Why Do Escalation Periods Exist?

As every Watson knows, audit contest judging is done by humans, which means it isn't perfect. The Lead Judge and the Sherlock Judge will try very hard, but sometimes even they make mistakes.

Sherlock sometimes receives a lot of re-judge requests after a contest's results are announced. Many times, the judges don't have time to go through all of them or prioritize them. And many of the re-judge requests end up being invalid, so judge time is wasted.&#x20;

As a Watson, this is a problem for you: If you think an issue was clearly misjudged by Sherlock, how can you make sure the judges know? What if it gets lost in the shuffle?

The Escalation Period exists so Watsons can make sure that misjudged issues are brought to light.&#x20;

### How Do Escalation Periods Work?

1-2 weeks after every contest, Sherlock announces the awards for the contest and opens up the judging repo to all Watsons to look through.

With the **Escalation Period** feature, there will now be a 48-hour window that opens as soon as awards are announced. During this 48-hour period, any Watson can "escalate" an issue directly in GitHub that they think was misjudged.

**Here's how it works:** Each Watson can make their escalations. Sherlock and the Lead Judge will go back and re-judge all escalations. This will make sure that the most important issues always get a second look. In the Escalation Period, Sherlock will have the final say instead of the Lead Judge.

Scenario #1: A Watson escalates an issue and the issue gets overturned (the Watson was correct). The overturned issue will get re-included in the awards and rankings. And the Watson's Escalations Ratio (see next section) will increase. \
\
Scenario #2: A Watson escalates an issue and the issue is not overturned (Watson was wrong about the issue). The issue will stay as it was (valid or invalid, etc.) and the Watson's Escalations Ratio (see next section) will decrease.&#x20;

### Earning the Ability to Submit Escalations

{% hint style="info" %}
Previously, escalations could be made by anyone and 10 USDC of a future payout would be at stake. Sherlock has transitioned away from this system starting on July 1st, 2023.&#x20;
{% endhint %}

There is no USDC cost to submitting an escalation, but there are 2 criteria that must be passed in order for a Watson to have the ability to submit escalations:

#### 1. Experienced Participant

In order to meet the "Experienced Participant" criteria you must have either:

1. Submitted 2 or more valid issues in an audit contest OR
2. Earned a USDC payout (made the leaderboard) in a judging contest

#### 2. Escalation Ratio

You must maintain >=20% on your Escalation Ratio.

The Escalation Ratio is calculated as:

{% code overflow="wrap" %}
```
(# of valid audit issues submitted + # of valid escalations submitted + # of judging contest payouts) / (total # of audit issues submitted + total # of escalations submitted + # of judging contest payouts)
```
{% endcode %}

These values will all be cumulative starting on July 1st, 2023 so one bad contest where you submit a lot of invalid issues or a lot of invalid escalations could prevent you from being able to submit new escalations for a long time! Be careful with how you approach this.

As long as a Watson meets or exceeds these two criteria (Experienced Participant and Escalation Ratio), then they will be able to submit escalations in any contest and on any issue. There is no USDC penalty for an incorrect escalation anymore. &#x20;

The purpose of this system is to limit the escalations to only the highest signal ones, and to limit the number of invalid escalations submitted to Sherlock as much as possible.&#x20;

### How Do I Escalate an Issue?

When a contest's awards are announced, the main judging repo is opened up to all participating Watsons. A Watson can see all of the issues that were submitted during the contest in the Issues tab in Github:

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

To escalate an issue, you can simply click on the issue you're interested in escalating, then create a comment on that issue that looks like this:

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Here's the template for your own escalation:

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
You must be in the 48-hour Escalation Period window in order to submit an escalation.&#x20;
{% endhint %}

If you submitted a successful escalation, you should receive a bot reply almost immediately:

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

As the "sherlock-admin" bot says, you can edit your escalation by editing the reason in the comment you've already posted. \
\
And you can delete an escalation by simply deleting the comment you've already posted. You should see a confirmation from the bot after a successful deletion:

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

### Rules for Escalation:

1. Escalation will not be accepted in case the reward distribution is not affected. \
   Example: If an escalation says \`This issue must be a duplicate of #23\` and if the main issue #23 is already a low/invalid issue and is not escalated. Then that escalation would be rejected since it would not affect reward distribution.&#x20;
2. You can combine multiple arguments related to the same issue into one escalation. This prevents getting a double penalty when the escalation is rejected. For example, you might argue that the issue is valid and should be duplicated with #4. \
   Also, you can mention multiple issues in the same escalation if they need to be duplicated together or separated from the context of the issue you are escalating. For example: 'The issues #12, #145 and #5 are all duplicates of the above issue'
3. If there were previous escalations for the same issue (let's say it's the second escalation), it won't be accepted unless the new argument proposes new changes or provides stronger reasons for the changes requested earlier.
4. Any request to resolve issues outside of the escalation period is not guaranteed to be addressed.&#x20;
