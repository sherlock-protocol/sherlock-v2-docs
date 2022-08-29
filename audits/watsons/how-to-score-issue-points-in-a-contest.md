# How you Score Issue Points in a Contest

The total Ranking Points which can be earned in a contest is the sum of the average Ranking Points of each competitor. In this way, Watsons aren’t given an unfair advantage or disadvantage if they compete in an audit with relatively weak or relatively strong participants.

Then, each Watson generates a score based on the amount of high and medium severity findings they submit. Note: In Sherlock contests, only Medium and High vulnerabilities count for Issue Points. There is no reward for submitting Low or Informational issues.

These are the “Issue Points” earned in a specific contest.

A Watson’s Ranking Points and payout from the prize pool is determined by calculating their share of all the Issue Points awarded, then multiplying their share by the total Ranking Points and Prize Pool available.

> _Watson1 Ranking Points = (Watson1 Issue Points Awarded / AllWatson Issue Points Awarded) \* (Total Ranking Points Available)_

> _Watson1 Prize Pool Award = (Watson1 Issue Points Awarded / AllWatson Issue Points Awarded) \* (Total Prize Pool Available)_

A Watson’s Issue Points earned is weighted based on severity and is calculated with sybil resistance in mind. To give credit where credit is due, the Code Arena team designed an innovative formula, which disincentivizes participants in their contest from submitting findings under multiple identities to try to earn more of the prize pool (i.e. sybil). They do this by awarding a greater pro-rata portion of the prize pool based on not only the _severity_ of the finding, but also the _uniqueness_. In instances where multiple people find the same issue, its cumulative score is less than if one person found it, effectively penalizing an individual who attempts to “sybil attack” a finding. As you can see, High issues are weighted 5x more heavily than Medium issues:

> _Medium Risk Local Points Weighting = 1 \* (0.9 ^ (IssueSubmissions - 1)) / IssueSubmissions_

> _High Risk Local Points Weighting = 5 \* (0.9 ^ (IssueSubmissions - 1)) / IssueSubmissions_
