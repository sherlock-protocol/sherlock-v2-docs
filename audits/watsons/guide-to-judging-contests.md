---
description: So you want to be a Sherlock judge...
---

# Guide to Judging Contests

## What's in it for you?

5% of the value of the audit contest pot will be up for grabs in each judging contest. If an audit has a $50k pot, then the “judging pot” will be $2,500.&#x20;

## When do judging contests start?

Immediately after an audit contest ends, the 3-day judging contest will begin.&#x20;

Example: If an audit contest goes from January 1st to January 14th, the judging contest will start on January 14th and run until January 17th.

## How to join a judging contest

1. Go to [https://app.sherlock.xyz/audits/contests](https://app.sherlock.xyz/audits/contests)
2. Sign up as a Watson if you haven't already.&#x20;
3. Find contests that have a pink "Judging contest" label.&#x20;
4. Click on that contest then click the "Judge contest" button on the lower right side.&#x20;
5. A new private repo will be created for you in GitHub.
6. The repo will contain a Markdown (.md) file with each submitted issue and two folders ("low" and "false"). Your job is to sort the Markdown files. See the next section.&#x20;

## How to judge issues

You've already completed the steps above and now you're ready to start judging:

For each Markdown (.md) file, you will:

1\. Decide the severity (High/Medium/Low/False)

* If High, create a new folder with issue number and an “H” (ex. 001-H) and put the corresponding .md file in the folder
* If Medium, create a new folder with issue number and an “M” (ex. 001-M) and put the corresponding .md file in the folder
* If Low/False, put the .md file in either the “low” or “false” folder

An example High severity issue might look like this:

![](https://lh6.googleusercontent.com/wEM\_XPnGmxNr6Ya8oTPWnCEX-U6hol0Qw6chciY64zozIP7yYzOuKzd7K5tGYjWmZo\_ZW71OvnyunUH\_DDiQCGC1ENYwxCQUGhUdP9-u0vAXYxM2b\_YBvv0jCJoxHucQcps7JHADRi-1XMpY2tV0yVo6HdUtIDCX91YTUIoVaG2eSHNguuleHulUXwCuDw)

2\. Decide if the issue is a duplicate or not

* If it’s a duplicate, put it in the same folder as an issue that it’s a duplicate of
* If it’s not a duplicate, it will live in its own folder (if it’s a High or Medium)

A family of duplicate High issues might look like:

![](https://lh6.googleusercontent.com/lummNF4RuBUR4F5GYyQn-IGIoDcfDkcIidFMvOdS0PIofIPlKhSdMu1CyiwLRfv2DyzipbjjkNvArhKotI9SIoXsBz5v7zLLboiKhhg1wKUg6JWD6EkJQI\_EW8dY9PKU6TLaW7QMZ4Bfz2rZD4sCWVd6Upt7FAcqHwq6OV1kGj4DC04ThDCT9flV6lKcvg)

3\. If there are duplicates, pick the “best” issue out of the bunch (the issue that describes the vulnerability best)

For example, if 7.md was the “best” issue, you would rename it like so:

![](https://lh3.googleusercontent.com/FT8dpErW4Y9eCrRa-x3BxhETjlKTTB4WuFXD5XT5rRDUtTOAwjaxVp5AGxwnlzLIYTXDh8LLAvJGUURSMkThhjvdVw8EHiudwh2PxG-zbBJw1G00mbaW\_5vddzT6Zw-BeXkuUvLTMldoo4fWfW4HjTs0qhw\_qvpcCwwcwrV4iJQi8HmkZmjBCy0XEDZrOg)

Once you’ve gone through all of the issues, every issue should be in a folder. The top-level folder structure might look like:\
\
001-H/\
002-H/\
001-M/\
002-M/\
003-M/\
low/\
false/

This would mean that there are 2 High severity vulnerabilities, and 3 Medium severity vulnerabilities.\
\
Once the issues have been sorted into folders and "best" reports labeled, you are done!

## How to earn USDC from judging

In order to become eligible for a payout, your judging must be >50% accurate. Each issue has 3 points:

1. Severity (Medium/High/else) = 1 point
2. Duplication (Is it in a folder with at least 1 correct duplicate issue? Or correctly put in a solo folder?) = 1 point
3. Best issue (Was the best issue of the duplicate family correctly chosen?) = 1 point

If there were 100 issues in a repo, and each issue is worth 3 points, then a contestant would need to get at least 150 points (150 correct / 300 possible = 50% score) in order to become eligible for a payout.

{% hint style="info" %}
Why is >50% accuracy required for a payout? If only 5% accuracy received a payout, then audit contest participants could just judge their own submissions and get paid for it, which is not fair.&#x20;
{% endhint %}

## How are USDC payouts calculated in a judging contest:

The formula for payouts is very similar to the sybil-resistant formula for audit contests.&#x20;

{% hint style="info" %}
Remember that in an audit contest, you get paid way more if you find an issue that no one else finds. The dynamic is the same in a judging contest.&#x20;
{% endhint %}

In the judging contest, you get paid way more if you get something correct that no one else gets correct. And you get paid less if 4 people get it correct vs. 2 people get it correct, etc.&#x20;

There’s also a twist:

1. Correct "Severity" judgments are worth 10x
2. Correct "Duplicate" judgments are worth 5x
3. Correct “Best Report” judgments are worth 1x

And the judging contest uses an even stricter sybil formula, which means getting a “solo correct” issue is worth A LOT more than getting an issue correct alongside 3 other people. Sherlock hopes this will reimburse judges who spend the time to understand the most difficult issues in the judging contest.&#x20;

The sybil-resistant formula is:

```
// question_weight / 2.01 ^ (X - 1)
```

Where question\_weight is the multiplier for the question type (Severity, Duplication, Best), and X represents the number of judges who got the question correct.&#x20;

After this, each judge will receive an individual score for their performance. And based on the individual\_score / total\_score, a proportional percentage of the contest pot will be awarded.

For example, if the contest pot is $2,500 and a judge receives 50% of all the points, then that judge will receive $1,250.&#x20;

\
\
\
\










\
\


\


