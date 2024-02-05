# How to Score Issue Points in a Contest

The total Contest Points which can be earned in a contest is the sum of the average Contest Points of each competitor (plus an inflation amount to offset new entrants). In this way, Watsons aren’t given an unfair advantage or disadvantage if they compete in an audit with relatively weak or relatively strong participants.

Then, each Watson generates a score based on the amount of high and medium severity findings they submit.&#x20;

> Note: In Sherlock contests, only Medium and High vulnerabilities count for Issue Points. There is no reward for submitting Low or Informational issues.

The points awarded for each issue submitted in a specific contest are called “Issue Points."&#x20;

A Watson’s Contest Points and payout from the prize pool is determined by calculating their share of all the Issue Points awarded, then multiplying their share by the total Contest Points and Prize Pool available.

> _Watson1 Ranking Points = (Watson1 Issue Points Awarded / AllWatson Issue Points Awarded) \*_ (Total Ranking Points Available)

> _Watson1 Prize Pool Award = (Watson1 Issue Points Awarded / AllWatson Issue Points Awarded) \* (Total Prize Pool Available)_

A Watson’s Issue Points earned is weighted based on severity and is calculated with sybil resistance in mind. The formula disincentivizes participants in the contest from submitting findings under multiple identities to try to earn more of the prize pool (i.e. a sybil attack). It does this by awarding a greater pro-rata portion of the prize pool based on not only the _severity_ of the finding, but also the _uniqueness_. In instances where multiple people find the same issue, the cumulative score is less than if one person found it, effectively penalizing an individual who attempts to “sybil attack” a finding. As you can see, High issues are weighted 5x more heavily than Medium issues:

> _Medium Risk Issue Points Weighting = 1 \* (0.9 ^ (IssueSubmissions - 1)) / IssueSubmissions_

> _High Risk Issue Points Weighting = 5 \* (0.9 ^ (IssueSubmissions - 1)) / IssueSubmissions_
