# How Audit Engine Works

An Audit Engine engagement follows five stages.

### 1) Connect and scope

Install the Sherlock GitHub app (or otherwise grant repo access as instructed). Pin the organization, repositories, branch, commit, and in-scope files or PRs.

Sherlock locks dates, participant set, and engagement parameters with you.

### 2) Add context

Provide materials that give context to findings in your system:

* Specs, READMEs, build and test instructions
* Invariants, actors / roles, and trust assumptions
* Prior audit reports and known issues

Context persists across runs when you reuse the same workspace. Known issues from prior Audit Engine runs can be excluded so participants do not re-report them.

{% hint style="info" %}
The more documentation you can provide, the better results you'll get. Missing or incomplete context can result in more work for your team since you'll receive more relevant findings that are less relevant.
{% endhint %}

### 3) Configure the run

Choose:

* Engagement shape (Sherlock will provide options)
* Package / participant mix (Sherlock will provide options)
* Start and end windows
* Rules and expectations around marketing and public engagement visibility
* Optional NDA requirement for participants

### 4) Run

Participants review the scope concurrently and submit findings through Audit Engine.

During the window you get:

* A live dashboard of submissions, findings, and activity feed
* Immediate alerts (Slack / email) for validated Critical and High findings
* Preliminary AI judge feedback, often within minutes, and expert Lead Judge feedback shortly thereafter
* Benchmarking of every participant across 20+ metrics, updated every second

### 5) Judging and results

Judging follows a staged pipeline:

1. Sherlock AI judge (validity, severity, deduplication, known issue check, in-scope check)
2. Lead Judge (oversight and edits on AI judge judgments)
3. Protocol team feedback and judgment updates

When the engagement is finished, you'll see finalized versions of:

* Curated **Findings** (including categories such as Invalid But Interesting)
* Downloadable **audit report**
* **Benchmarking** report (20+ metrics stack-ranking every participant on the codebase)
* Payout snapshot on a stated date (participant rewards)

### Typical timelines

Exact dates are set in your SOW or engagement card. Patterns observed across engagements include:

| Shape                                         | Illustrative pattern                                                                                           |
| --------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Focused sprint AI engagement                  | Concentrated number of AI participants and you'll see results in hours                                         |
| Comprehensive-style AI engagement             | Larger-scale AI engagement where initial results are seen in hours and judging can take an extra day           |
| Intensive AI + Security Researcher engagement | Multi-day engagements where the "kitchen" sink is thrown at the codebase and judging lasts an extra day or two |

Treat these as **ranges and examples**, not hard rules. Audit Engine is generally flexible to custom setups. Sherlock recommends windows per engagement based on scope size, tool runtime, time zones, and other factors that can influence a successful engagement.

***
