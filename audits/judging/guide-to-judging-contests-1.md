---
description: So you want to be a Sherlock judge...
---

# Participating in Judging Contests (July 1st, 2023)

## What's in it for you?

5% of the value of the audit contest pot will be publicly available. If an audit has a $50k pot, then the portion of the “judging pot” that will be publicly available is $2,500.

The Lead Judge will also receive 5% of the audit contest pot. Here is how you can become a [Lead Judge](lead-judge-selection-process.md).

## When do judging contests start?

Immediately after an audit contest ends, the judging contest will begin. The judging contest will be contingent on the number of issues. More specifically, one day will be added per 75 issues submitted in the contest (200 issues = 3-day judging contest, 250 issues = 4-day judging contest).

## How to join a judging contest

1. Go to [https://app.sherlock.xyz/audits/contests](https://app.sherlock.xyz/audits/contests)
2. Sign up as a Watson if you haven't already.
3. Find active contests in the `JUDGING CONTESTS` section of the [Contests page](https://app.sherlock.xyz/audits/contests), or find upcoming ones by looking for a "Judge Contest" button on a protocol's detailed contest page
4.  Click on that contest then click the "Judge Contest" button on the lower right side.\


    <figure><img src="../../.gitbook/assets/image (3) (3).png" alt=""><figcaption></figcaption></figure>
5. A new private repo will be created for you in GitHub.
6. The repo will contain a Markdown (.md) file with each submitted issue. Your job is to sort the Markdown files. See the next section.

## How to judge issues

{% hint style="danger" %}
**DONT's**

* Change file content
* Remove files (only move between folders)
* Rename files (has a single exception)
* Create folders that are not formatted either ###-M or ###-H

\### stands for any number, we would suggest to start with 001 and increase sequentially (002, 003, 004)

By default every {number}.md file in the root of the repo is considered an unjudged issue.
{% endhint %}

You've already completed the steps above and now you're ready to start judging:

For each Markdown (.md) file, you will:

{% hint style="danger" %}
Sherlock judges low, info and false issues as invalid
{% endhint %}

1\. Decide the severity (High/Medium/Invalid)

* If High, create a new folder with a 3 digit number and an “-H” (ex. 001-H) and put the corresponding .md file in the folder
* If Medium, create a new folder with a 3 digit number and an “-M” (ex. 001-M) and put the corresponding .md file in the folder
* If Invalid, keep the .md file in the root (or create a “invalid” folder to keep track of them yourself)

An example High severity issue might look like this:

```
Individual issue

001-H/
  - 003.md
```

2\. Decide if the issue is a duplicate or not

* If it’s a duplicate, put it in the same folder as an issue that it’s a duplicate of
* If it’s not a duplicate, it will live in its own folder (if it’s a High or Medium)

A family of duplicate High issues might look like:

```
Family of issues

001-H/
  - 003.md
  - 007.md
  - 049.md
```

3\. If there are duplicates, pick the “best” issue out of the bunch (the issue that describes the vulnerability best)

For example, if 7.md was the “best” issue, you would rename it like so:

```
Family of issues (with best issue labeled)

001-H/
  - 003.md
  - 007-best.md
  - 049.md
```

Once you’ve gone through all of the issues, every issue should be in a folder. The top-level folder structure might look like:

```
001-H/
002-H/
001-M/
002-M/
003-M/
```

This would mean that there are 2 High severity vulnerabilities, and 3 Medium severity vulnerabilities.\
\
If you were to open up all the folders above, it might look like this:

```
001-H/
  - 003.md
  - 005-best.md
  - 012.md
002-H/
  - 006.md
001-M/
  - 007.md
  - 013-best.md
002-M/
  - 011-best.md
  - 016.md
003-M/
  - 014.md
- 001.md
- 002.md
- 004.md
- 008.md
- 009.md
- 010.md
- 015.md
```

This structure still means that there are 2 High severity vulnerabilities, and 3 Medium severity vulnerabilities (just like the top-level folder structure above).

{% hint style="info" %}
"-best" only needs to be added when there is more than 1 .md file in a folder.
{% endhint %}

Once the issues have been sorted into folders and "best" reports labeled, you are done!

## How to earn USDC from judging

Great, so you've organized all the issues in the judging repo according to the instructions above. Let's get you paid!

### You must clear 3 thresholds to be eligible for USDC

In order to be eligible for payment, your judging repo must pass the following 3 thresholds. This helps prevent random or low-effort judging repo submissions from earning USDC.&#x20;

1. **Recall Threshold:** How many of the important vulnerabilities (families) would your repo have shown to the protocol team?
   * Must score >=80%
2. **Precision Threshold:** Out of all the issues you showed (# of issue families), how many were invalid or unnecessary to show?
   * Must score >=20%
3. **Duplicates Threshold:** Out of all the potential issues, how many did you duplicate into the correct family (or correctly mark as "invalid")?
   * Must score >=20%

If you clear these 3 thresholds, your judging repo will be eligible for a USDC payout!

Let's look at the 3 thresholds in more depth:

#### Recall Threshold

The Recall Threshold formula asks: How many of the important vulnerabilities (families) would your repo have shown to the protocol team?

Let's assume there are 5 total High/Medium families in the final state of a contest. If your repo showed all 5 families as High/Medium, you get 100% on the Recall Threshold formula!!&#x20;

If you show 4 out of 5, then you get 80% (4 divided by 5) on the Recall Threshold formula, etc.

Sherlock refers to these "important vulnerabilities" as "families" since they may have duplicates in their folder. For example, one of the families might look like this:

```
001-H/
  - 003.md
  - 005-best.md
  - 012.md
```

^We'll call this the "truth" repo (the final state of a contest's judging repo). If your own judging repo showed any of the above 3 issues (003.md, 005.md, 012.md) as a "best" issue, then you'll get credit for getting this entire family correct in the Recall Threshold formula.&#x20;

The full "truth" repo with all 5 families (and 7 invalid issues) might look like this:

```
001-H/
  - 003.md
  - 005-best.md
  - 012.md
002-H/
  - 006.md
001-M/
  - 007.md
  - 013-best.md
002-M/
  - 011-best.md
  - 016.md
003-M/
  - 014.md
- 001.md
- 002.md
- 004.md
- 008.md
- 009.md
- 010.md
- 015.md
```

In order to get 100% on the Recall Threshold formula, you could have put each of 012.md, 006.md, 013.md, 016.md, and 014.md into their own folder and marked them as the best issue in that folder. If you also put 003.md or 005.md into their own folders (and marked them "best) you'd still get 100% on the Recall Threshold formula (the next formula will penalize you for showing the same vulnerability twice as a "best" issue).&#x20;

#### Precision Threshold

The Precision Threshold formula asks: Of all the "best" issues you submitted, how many of them ended up being a real issue according to the final state of the judging repo?

For example, if you submitted 10 families (each with its own "best" issue in it) but only 4 of them ended up being real vulnerabilities, then you'd score 40%. Out of the other 6 families, 4 of them could have been showing invalid issues and 2 of them could have been unnecessary showing a duplicate of the 4 real vulnerabilities.&#x20;

{% hint style="info" %}
You can only get credit for each real vulnerability category once.
{% endhint %}

For example, if we had the same "truth" repo from above:

```
001-H/
  - 003.md
  - 005-best.md
  - 012.md
002-H/
  - 006.md
001-M/
  - 007.md
  - 013-best.md
002-M/
  - 011-best.md
  - 016.md
003-M/
  - 014.md
- 001.md
- 002.md
- 004.md
- 008.md
- 009.md
- 010.md
- 015.md
```

If you submitted every single issue (001.md through 015.md) as its own family (marked all 15 issues as "best") then you would get 5 out of 15 correct (33% score). 001.md would not be rewarded because it was invalid. Same with 002.md. You'd get credit for 003.md because it's a valid issue in a valid family in the truth repo. No credit for 004.md. And you also wouldn't get credit for 005.md because you had already gotten credit for that family when you marked 003.md as a "best" issue in its own family.&#x20;

#### Duplicates Threshold

Duplicates Threshold asks: Out of all the potential issues, how many did you duplicate into the correct family (or correctly mark as "invalid")?

An intermediate way to understand Duplicates Threshold is:

\# of valid issues you duplicated correctly / (# of valid duplicates in the "truth" + # of invalid issues you duplicated into a valid family)

What exactly is a "correct" duplication? A particular issue is duplicated correctly when:

1. The issue is valid
2. The "best" issue in its family (in your judging repo) is also grouped in the same family as your particular issue in the "truth" repo

To explain #2: If 002.md is put into a family where 001.md is marked "best" (001-best.md) then Sherlock checks to see if 001.md and 002.md are also grouped in the same family in the "truth" repo. If they are, then you'd get credit for it.&#x20;

Sherlock tallies your correct answers in the numerator and the denominator is the total number of valid duplicates possible in the truth repo. However, Sherlock penalizes you (by adding to the denominator) each time you add a false issue into a valid family.

#### Strategy for clearing the 3 Thresholds

As you may notice there is a MUCH higher bar (80%) for Recall Threshold vs. the other 2 (20%). That's because if you score less than 100% on Recall Threshold, it would mean that a real vulnerability wouldn't have been shown to the protocol team. This is REALLY BAD and could result in the protocol team going to mainnet with a vulnerability that they weren't told about, and an exploit could occur. This is why Recall Threshold ("did you show all important issues to the protocol team?") is so important.&#x20;

That's why Recall Threshold is at 80% while the other two are at 20%.&#x20;

Messing up on Precision Threshold means Sherlock shows an extra family to the protocol team. This is really not a big deal.&#x20;

And messing up Duplicates Threshold means a Watson's issue doesn't get correctly categorized and they aren't paid accurately for it. This is not ideal, but that Watson will have the ability to escalate their issue and hopefully get it corrected.&#x20;

The best strategy for clearing the 3 thresholds is to focus on making sure no important vulnerabilities are hidden from the protocol team, and the 20% Precision Threshold will give you a lot of room for error when it comes to showing too many families to a protocol team. The best strategy is to "play it safe" and show issues in separate families to the protocol team whenever you aren't sure if the issue is real or not.&#x20;

### Payout Calculation

Welcome!! Hopefully you submitted a great repo and passed the 3 thresholds. Now let's figure out how much you should get paid vs. others.&#x20;

Because there's no limit to the amount of Watson accounts that can submit a judging repo, Sherlock needs to apply a sybil formula to penalize answers that are more common than others. Wrong answers will always get 0 points. Popular correct answers will get a small # of points. And unpopular correct answers will get significantly more points.&#x20;

Your score will be the aggregation of the 6 different categories. Your score will be determined by:

1. Whether you got each answer correct
2. How many others got the same answer correct (sybil protection)
3. The sum of your scores (after the sybil formula) for each correct answer in the category
4. The weighting of that category among the 6 categories
5. The sum of your total scores for each category

### The 6 categories that determine how much USDC you'll earn

#### 1. Sybil Recall

The Sybil Recall category will determine **90% of your final score**. That's right. The other 5 categories will split the remaining 10%. This is **THE MOST IMPORTANT CATEGORY** when it comes to earning USDC.&#x20;

And it's very similar to Recall Threshold, discussed above:

> "How many of the important vulnerabilities (families) would your repo have shown to the protocol team?"

Here's a slightly more technical description:

> Loop through all families in the "truth" repo. For each family you get +1 if at least 1 of the issues in that truth family is submitted as a "best" issue. There's no extra credit for submitting 2 or more of the issues in a particular truth family as a "best" issue.&#x20;
>
> For each +1, first Sherlock runs it through the sybil formula (discount it if multiple people got it right). Then Sherlock adds up all your discounted points from this category.

It's the exact same thing as the Recall Threshold, except with a sybil formula applied to each correct answer, so the more people who get each individual answer correct, the less that answer is worth. See the Recall Threshold section above for an example of how this category works (minus the sybil part).&#x20;

#### 2. Sybil Precision Family&#x20;

The general idea of this category (and the 3rd category) is the same as Precision Threshold:&#x20;

> "Of all the "best" issues you submitted, how many of them ended up being a real issue according to the final state of the judging repo?"

However, adding sybil-resistance makes it much more complicated.&#x20;

Sybil Precision Family therefore only focuses on how many unnecessary valid issues you showed to the protocol team. For example, two issues are valid and should be duplicates of each other in the same family. Sybil Precision Family gives you credit if you group them together into the same family, and no credit if you showed them as separate families.&#x20;

Here's the technical way this category is scored:

> Loop through all families in the truth repo. Loop through each family “# of issues in family - 1” times. For each inner loop within each family, count the loop # and you get +1 if you submitted any of the issues in that truth family “loop #” or less times.
>
> For each +1, first we run it through the sybil formula (discount it if multiple people got it right). Then we add up all your discounted points from this formula.&#x20;

Here's an example for 1 family in the truth repo:

```
001-H/
  - 003.md
  - 005-best.md
  - 012.md
  - 018.md
```

This truth family has 4 issues in it. Therefore we'll ask:

> Did you submit 1 issue (or less) in this family as a "best" issue in a family?
>
> Did you submit 2 issues (or less) in this family as a "best" issue in a family?
>
> Did you submit 3 issues (or less) in this family as a "best" issue in a family?

The question is only asked up to "# of issues in family MINUS 1" times because otherwise a judge who submitted each issue as its own family would get credit.&#x20;

#### 3. Sybil Precision Invalid

This category is the "other half" of the Sybil Precision Family. It works the same way except for invalid issues. It asks:

> Did you avoid submitting invalid issues as "best" issues?

Here's the more technical description:

> Loop through all invalid issues in the truth repo, +1 for each issue that is not submitted as "best" in the your repo.
>
> For each +1, first Sherlock runs it through the sybil formula (discount it if multiple people got it right). Then Sherlock adds up all your discounted points from this category.&#x20;

#### 4. Sybil Duplicates Valid

This category and the next one are both very similar to Duplicates Threshold:

> Out of all the potential issues, how many did you duplicate into the correct family (or correctly mark as "invalid")?

Except Sybil Duplicates Valid only focuses on asking this question for valid issues in the truth repo.&#x20;

Here's how it works technically:

> Loop through all valid issues in the truth repo. For each issue (issue A, etc.) find its family in the your repo. That family has a "best" issue. If issue A and the "best" issue are in the same family in the truth repo, you get +1.
>
> For each +1, first Sherlock runs it through the sybil formula (discount it if multiple people got it right). Then Sherlock adds up all your discounted points from this category.&#x20;

And a few important edge cases:

> * Note #1: If you submit issue A as a solo and it's also a solo in the truth repo, you get points&#x20;
> * Note #2: If you submit issue A as a solo and it's NOT a solo in the truth repo, no points
> * Note #3: If issue A IS the best-report issue, then issue A and another issue in your submitted family must live in the same family in the truth repo in order to get points
> * Note #4: If you submit issue A as invalid, you get no points

#### 5. Sybil Duplicates Invalid

This is the other half of Sybil Duplicates Valid. It asks the same question but for the invalid issues in the truth repo:

> Loop through all invalid issues in the truth repo, for each issue +1 if it is submitted as an invalid issue or submitted in a family where the "best" issue is referring to an invalid issue in the truth repo.&#x20;
>
> For each +1, first Sherlock runs it through the sybil formula (discount it if multiple people got it right). Then Sherlock adds up all your discounted points from this category.&#x20;

It's important to note that if you thought a family of issues were valid, but it turns out they were invalid, you'll still get credit for all of the correct duplicates in that family of invalid issues in this category.

#### 6. Sybil Severity

This is the final category and it has no parallel in the Threshold formulas. It simply asks:

> If you got a valid family correct, +1 if you also correctly labeled it "High" or "Medium".&#x20;

Here's the technical explanation:

> Loop through all valid issues in the truth repo, for each issue +1 if the severity (High/Medium) in the truth repo matches the severity (High/Medium) of the submission family in which that issue was submitted. No credit for invalid issues.&#x20;
>
> For each +1, first Sherlock runs it through the sybil formula (discount it if multiple people got it right). Then Sherlock adds up all your discounted points from this category.&#x20;

### Summing the 6 Categories

Phew, you made it through the descriptions of the 6 categories. You may have already noticed that the Sybil Recall category will always be worth 90% of each Judge's total score. That's a lot and it will definitely pay to focus on that category!!

But how are the weightings between the other categories determined?

They're determined based on 2 factors:

1. The number of possible points in that category
2. A weighting assigned by Sherlock

For #1, the number of possible points is simply the number of questions asked in that category. For example, Sybil Duplicates Invalid loops through all the invalid issues so the number of questions (and possible points) in that category is the total # of invalid issues in the truth repo.&#x20;

It's probably easiest to understand this dynamic if you can see the full formulas and play around with the numbers yourself (make a copy of this Google sheet):

{% embed url="https://docs.google.com/spreadsheets/d/16Jr5bztIHXZhdf5TG-XW7p7MC_mLoReCvtYjbBwr3YI/edit?usp=sharing" %}

As you can see, the possible points is very heavily dependent on the number invalid/valid issues and the number of valid families.&#x20;

Here are the current weightings/values chosen by Sherlock:

| Categories               | Weighting | % of Total Score |
| ------------------------ | --------- | ---------------- |
| Sybil Recall             | Dynamic   | 90%              |
| Sybil Precision Family   | 3.0x      | Dynamic          |
| Sybil Precision Invalid  | 4.0x      | Dynamic          |
| Sybil Duplicates Valid   | 3.0x      | Dynamic          |
| Sybil Duplicates Invalid | 3.0x      | Dynamic          |
| Sybil Severity           | 1.0x      | Dynamic          |

### Judging Payout Recap

To summarize, here are the steps to know your payout for a judging contest:

1. Did you sign up for the judging contest and categorize issues to the best of your ability?
2. Did your repo pass all 3 thresholds in order to be eligible for any USDC?
3. For each possible point in each of the 6 payout categories, did you get the question correct?
4. For each possible point in each of the 6 payout categories, how many others got the question correct?
5. What was your summed score in each of the 6 categories?
6. What was your total score after applying the weights to each category, figuring out the % of total score contributed by each category and summing up the result?
7. Figure out many others cleared the 3 thresholds and figure out their total score (after step 6)
8. For all the total points scored by each participant, what % of that total did your score make up? For example, if it made up 10%, then you'll earn 10% of the judging rewards pot!

## How to move up the Judging Leaderboard

The judging leaderboard will work much like the Audit Contest Leaderboard.&#x20;

Every participant who signs up for the judging contest will be putting their points at risk (no ability to opt out).&#x20;

Whatever % of the total points you earned in that judging contest (based on the same criteria used above to calculate USDC payouts) will also be the % of the Judging Contest points that you'll earn for that contest.&#x20;

Your last 70 days worth of Judging Contest points will be counted. For the points earned in each judging contest, your Judging Leaderboard Points will be weighted by the length of the judging contest (not the length of the audit contest).&#x20;

For example, if you earned 100 points in a 10-day judging contest and 300 points in a 5-day judging contest, then your total Judging Leaderboard Points will be:

```
((10/15)*100)+((5/15)*300) = ~166.67 Leaderboard Points
```

You'll have more opportunities to be the Lead Judge for a contest the higher you move up the Judging Leaderboard. Good luck!!
