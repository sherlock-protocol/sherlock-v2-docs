# Escalation Period

{% hint style="info" %}
For instructions on how to escalate an issue, please see[#how-do-i-escalate-an-issue](escalation-period.md#how-do-i-escalate-an-issue "mention")
{% endhint %}

### Summary

As a Watson, if you participate in an audit contest, submit issues and then think your issues (or others' issues) were not properly judged, you can stake some amount of USDC and escalate the issue back to Sherlock, where the judges will re-review it.&#x20;

### Why Do Escalation Periods Exist?

As every Watson knows, audit contest judging is done by humans, which means it isn't perfect. Sherlock judges are extremely good, but sometimes even they make mistakes.

Sherlock sometimes receives a lot of re-judge requests after a contest's results are announced. Many times, the judges don't have time to go through all of them or prioritize them. And many of the re-judge requests end up being invalid, so judge time is wasted.&#x20;

As a Watson, this is a problem for you: If you think an issue was clearly misjudged by Sherlock, how can you make sure the judges know? What if it gets lost in the shuffle?

The Escalation Period exists so Watsons can make sure that misjudged issues are brought to light.&#x20;

### How Do Escalation Periods Work?

1-2 weeks after every contest, Sherlock announces the awards for the contest and opens up the judging repo to all Watsons to look through.

With the **Escalation Period** feature, there will now be a 48-hour window that opens as soon as awards are announced. During this 48-hour period, any Watson can "escalate" an issue directly in GitHub that they think was misjudged.

**Here's how it works:** Each Watson will stake a 10 USDC amount to their escalation. Sherlock and the Lead Judge will go back and re-judge all escalations for $10. There is no maximum amount of escalations. This will make sure that the most important issues always get a second look by Sherlock and the Lead Judge.

Scenario #1: A Watson escalates an issue, stakes 10 USDC and the issue gets overturned (the Watson was correct). The overturned issue will get re-included in the awards and rankings. And the Watson will not lose any of that 10 USDC.\
\
Scenario #2: A Watson escalates an issue, stakes 10 USDC, and the issue is not overturned (Watson was wrong about the issue). The 10 USDC is removed from the Watson's payout in that contest or the next contest where they receive a payout.

### How Do I Escalate an Issue?

When a contest's awards are announced, the judging repo is opened up to all participating Watsons. A Watson can see all of the issues that were submitted during the contest in the Issues tab in Github:

<figure><img src="../../.gitbook/assets/image (11) (1).png" alt=""><figcaption></figcaption></figure>

To escalate an issue, you can simply click on the issue you're interested in escalating, then create a comment on that issue that looks like this:

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>Example escalation</p></figcaption></figure>

Here's the template for your own escalation:

<figure><img src="../../.gitbook/assets/image (2) (2).png" alt=""><figcaption><p>Template for an escalation</p></figcaption></figure>

{% hint style="info" %}
You must be in the 48-hour Escalation Period window in order to submit an escalation.&#x20;
{% endhint %}

If you submitted a successful escalation, you should receive a bot reply almost immediately:

<figure><img src="../../.gitbook/assets/image (3) (2).png" alt=""><figcaption></figcaption></figure>

As the "sherlock-admin" bot says, you can edit your escalation by editing the USDC amount or reason in the comment you've already posted. \
\
And you can delete an escalation by simply deleting the comment you've already posted. You should see a confirmation from the bot after a successful deletion:

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption><p>Successful deletion of an escalation</p></figcaption></figure>

### Who Keeps the Escalation Stake?

If a Watson stakes 10 USDC and escalates an issue, there are two outcomes:&#x20;

1\) The Watson is correct, the issue's classification changes, and the Watson keeps their 10 USDC

2\) The Watson is incorrect, the issue stays the same, and the Watson loses their 10 USDC stake

In scenario #2, the 10 USDC is simply added back to the contest pool and split equally among all other Watsons who earned points in the contest. If Sherlock kept this 10 USDC, it would create an incentive for Sherlock to deny escalations, and that would be bad.&#x20;

{% hint style="info" %}
If a Watson stakes 10 USDC, loses the escalation and ALSO didn't earn anything in the contest, then a debt will be carried on the Watson's account until they earn USDC in a future contest. In this case, future contest participants would receive the USDC, not current contest participants.&#x20;
{% endhint %}

### How Does Sherlock Protect Against Sybil Attacks on the Escalation Period?

With this setup, a Watson could simply escalate 1000 issues for 10 USDC to make sure the judges re-judge them. If they lose, then they accrue a 10,000 USDC debt on their account, but the Watson will just create a new account.\
\
If this becomes a problem, Sherlock may:

1. Only allow Watsons with past contest history to escalate issues.&#x20;
2. Watsons must put down a small deposit (maybe 20 USDC) in order to participate in the contest in the first place.&#x20;
