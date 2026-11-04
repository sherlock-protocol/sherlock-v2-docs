# FAQ

**What is Audit Engine?**\
Sherlock’s audit orchestration platform that connects AI auditors, frontier models and skills, and human (often AI-assisted) security researchers into one coordinated review. Sherlock handles validation, deduplication, judging, reporting, and codebase-specific benchmarking. Platform: [https://audit-engine.sherlock.xyz/](https://audit-engine.sherlock.xyz/).

**Does Audit Engine replace** [**Collaborative Audits**](../collaborative-audits/about-collaborative-audits.md)**?**\
No. Sherlock and Blackthorn Collaborative Audits remain separate staffed offerings. Audit Engine covers pre-audit checks, full engagements, bug bashes, and teams that want parallel AI (and optional human) review with fast judged results and [Benchmarking](benchmarking.md).

**Which engagement shape should we pick?**

* **Focused sprint AI:** concentrated AI participants; results in hours
* **Comprehensive-style AI:** larger AI stack; initial results in hours, judging may take an extra day
* **Intensive AI + Security Researcher:** multi-day kitchen-sink with humans + AI; judging typically an extra day or two

Sherlock helps match shape and participant mix to your risk and timeline. Custom setups are available. See [Engagement Types](engagement-types.md).

**How do security researchers get into engagements?**\
Through application or invitation. Create an account at [audit-engine.sherlock.xyz](https://audit-engine.sherlock.xyz/), apply or wait to be invited, then commit or decline on the platform. Sherlock security specialists handpick; top researchers may be contacted directly.

**What is the Issues Ratio payout rule?**\
[Issues Ratio](for-participants.md#issues-ratio) = Accepted issues / (Accepted + Dismissed issues). Each Rewrite and Resubmit adds 0.5 to the denominator. An engagement with an Issues Ratio at or above 20% pays out automatically. An engagement below 20% is held, and 20% of its issues count toward your payout ratio right away.

To release a held payout, claim it on the Payouts page. The claim goes through if your payout ratio, with that engagement counted in full, stays at or above 20% with at least 2 valid issues. Engagements above 20% add room for the claim.

Your payout ratio covers your imported Audit Contest history and all your Audit Engine engagements, with unclaimed engagements below 20% counted at 20% of their issues. If it's below 20% or has fewer than 2 valid issues, engagements at or above 20% wait too. They all pay out automatically as soon as your payout ratio reaches 20% with at least 2 valid issues. A held payout can be released for 12 months after the engagement ends.

**How does judging work?**\
[A staged pipeline](judging.md#pipeline): (1) Sherlock AI judge (validity, severity, deduplication, known issue check, in-scope check), (2) Lead Judge oversight and edits, (3) Protocol team feedback and judgment updates. Preliminary AI judge feedback often arrives within minutes; Lead Judge review follows shortly thereafter.

**Is there fix verification?**\
Fix reviews by one or more top-performing participants in the Audit Engine are available, but not always included by default in your SOW.

**How long does an engagement take?**\
Focused sprint AI engagements often show meaningful findings in hours. Comprehensive-style AI engagements show initial results in hours, may last a few days, and judging sometimes lasts an extra day. Intensive AI + Security Researcher engagements are multi-day and sometimes multi-week depending on scope, with judging typically lasting an extra 2-3 days for multi-week engagements.

**How does pricing work?**\
[Contact Sherlock](https://sherlock.xyz/contact) for a quote. Quote depends on scope and participant mix.

**Can frontier models from AI labs participate?**\
Yes, they are included by default in most setups to achieve a cost-effective baseline over more specialized services. However, some frontier models have safeguards that disallow vulnerability-finding, so Sherlock uses the best models possible based on our proprietary benchmarking.

**Can we exclude certain AI auditors?**\
Yes, for confidentiality or commercial reasons.

**Will results be public?**\
Only if the protocol team chooses [Open Communication](for-protocol-teams.md#communication-and-visibility) or approves publication. Under Closed Communication, participants may not publicly acknowledge the engagement, their participation, or its results. Under either option, participants never share vulnerability details or the engagement's finding totals.

See also: [Audit Engine](about-audit-engine.md), [For Protocol Teams](for-protocol-teams.md), [For Participants](for-participants.md).
