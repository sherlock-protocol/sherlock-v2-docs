---
description: A Hypothetical Walkthrough of How Leaderboard Points are Calculated
---

# Watson Points Example

First, you can find the Sherlock leaderboard [here](https://app.sherlock.xyz/audits/leaderboard).&#x20;

How are those leaderboard points calculated? And how you can move up the leaderboard as a security expert?

### **Where do leaderboard points come from?**

1\) If you've competed in Code Arena before (and you signed up with the same ETH address), we give you temporary leaderboard points based on your best 5 performances in Code Arena (using Sherlock's ranking methodology).\
\
2\) If you've never competed in Code Arena, then you are given temporary leaderboard points that represent the median leaderboard points of all Sherlock participants (Watsons).&#x20;

> Spoiler: Your temporary leaderboard points don't really matter. You don't get credit for them and they won't cause you to show up on the leaderboard either.&#x20;

Temporary leaderboard points are simply a way of initiating your account into the Sherlock ranking system. \
\
In this example, Alice, Bob, and Carol had competed in Code Arena before, so their temporary leaderboard points came from there. Dan and Emily had never competed in Code Arena, so their accounts were initialized with the median leaderboard points of all Sherlock competitors. Again, your temporary leaderboard points don't really matter and you don't get credit for them, so don't worry too much about them.&#x20;

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Next, Alice, Bob, Carol, Dan, and Emily compete in a Sherlock contest. It's a 7-day contest and at the end of the contest, there are 4 legitimate findings. Two of them are High severity and two of them are Medium severity. The "1"s represent whether the participant submitted a particular finding or not. As we can see, Alice submitted the H1 and M1 findings, and so did Carol. H1 represents the first High severity finding and M1 represents the first Medium severity finding.&#x20;

<figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

Here are the "sybil-resistant" formulas used to calculate how many "issue points" each participant gets for each finding:

> _Medium Risk Issue Points Weighting = 1 \* (0.9 ^ (IssueSubmissions - 1)) / IssueSubmissions_

> _High Risk Issue Points Weighting = 5 \* (0.9 ^ (IssueSubmissions - 1)) / IssueSubmissions_

As you can see, High severity issues are initially worth 5x more than Medium ones. But the final "issue points" awarded to each person depend heavily on how many others found the same issue. \
\
Here's how that same table from above looks using the "issue points" formulas:

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

As you can see, Bob was the only person to find H2 (a High severity issue) and he was awarded the most points out of anyone because of it. H1 was significantly less fruitful because three people found it instead of just one.

Based on these "issue points," we can now see who performed best in the contest and earned the most from the USDC pot:

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Bob makes over 50% of the contest pot (over 50k USDC), largely driven by his submission of H2, which no one else found. Emilly fared the worst because she only found Medium severity issues, and other participants also found both Medium severity issues.&#x20;

Based on % of the pot captured by each participant, we can now calculate their leaderboard points. Everyone was assigned temporary leaderboard points because this was everyone's first contest. And the temporary leaderboard points are simply re-distributed based on who performed the best in the contest (captured the largest % of the pot):

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

We can see that Bob emerged as a winner and gained \~155 points thanks to this contest. This is because he captured \~51% of the total pot, mostly driven by his solo submission of H2, a High severity issue that no one else found. Emily only had 50 points going into the contest, so she only lost \~3 points despite a relatively poor performance in the contest. Alice took a large hit, parting with \~195 points. Expectations for Alice were high based on her Code Arena performances (giving her the 300 temporary leaderboard points) but she did not live up to expectations in this contest, so her leaderboard points took a big hit.&#x20;

Just to make the walkthrough extra clear (and add some complexity at the end), we'll show an example of the same 5 participants taking their true leaderboard scores and competing in a second contest. This second contest is 14 days long instead of 7 days like the previous one, which will be important for calculating leaderboard points at the end.&#x20;

We can see a new distribution of findings in the second contest, with 1 legitimate High severity issue found and 4 legitimate Medium severity issues found:

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Using the "sybil-resistant" formula from above, we can see that Carol and Emily performed the best in this contest:

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

We can see that almost 60% of the 200k USDC pot was distributed for the H1 finding:

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Now comes a bit of complexity. The 5 participants have completed a 7-day contest and a 14-day contest. Sherlock's scoring system puts a greater weight on the 14-day contest (2x weight to be exact) because it was a longer contest with a presumably larger codebase. So we'll take the old leaderboard points of all 5 participants (based on the 7-day contest) and weigh them against the new performances in the 14-day contest. As a reminder, points gained in the 14-day contest are relative to the % of the pot captured. Emily captured the highest % of the pot in the 14-day contest at \~34%, so she could see the biggest benefit from the second contest. However, the first contest will still make up 1/3rd (7 days out of 21 days total) of her score. \
\
The formula being used to calculate Emily's score is the following:

> (46.8 \* (7 / 21)) + ((33.7% \* 700) \* (14 / 21))

The 700 represents the cumulative amount of leaderboard points in the second contest from all the competitors. This is a simplified example where only the same 5 competitors happened to compete in both contests.&#x20;

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

This is how the Sherlock leaderboard would look after these two contests:

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

Because of the increased weighting of the 14-day contest vs. the 7-day contest, Carol and Emily ended up higher on the leaderboard than Bob, despite Bob's great performance in the 7-day contest.&#x20;
