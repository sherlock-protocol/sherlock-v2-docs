---
description: >-
  Guidance for audit contest duration based on scope size, plus what to budget
  for judging, remediation, and fix verification after the contest.
---

# Audit Contest Timeline

Audit contests are scheduled around scope size, architecture complexity, and launch risk. Sherlock uses a mix of designated senior review and broad independent researcher participation, then runs live judging during the contest so findings stay clean and actionable.

This page provides planning guidance for contest length based on codebase size. Final duration is set during scoping.

#### Planning guidance by codebase size

Sherlock estimates size using nSLOC (non-comment source lines of code), calculated using Solidity Metrics.

_Note: The sizing guidance below is based on Solidity nSLOC (measured with Solidity Metrics) and is meant for EVM/Solidity scopes. For non-Solidity codebases (for example, Solana programs in Rust) and for mixed-language systems, Sherlock scopes timeline and review length based on program structure, attack surface, and integration complexity rather than nSLOC._

<table data-header-hidden><thead><tr><th width="229">Solidity Lines (nSLOC)</th><th width="145">Audit Timeline</th></tr></thead><tbody><tr><td>~500</td><td>~3 days</td></tr><tr><td>~1000</td><td>~6 days</td></tr><tr><td>~2000</td><td>~12 days</td></tr><tr><td>~3000</td><td>~18 days</td></tr><tr><td>~4000</td><td>~25 days</td></tr><tr><td>~5000</td><td>~32 days</td></tr><tr><td>~6000</td><td>~38 days</td></tr></tbody></table>

> Note: Sherlock utilizes the tool [Solidity Metrics](https://github.com/ConsenSys/solidity-metrics) to calculate nSLOC.\
> \
> \*Given the exponential complexity of very large codebases for any security expert, Sherlock will have final discretion whether to write smart contract coverage behind its audit for protocols with >6000 nSLOC

For very large codebases, duration is not purely linear. Sherlock will confirm scope boundaries and expected throughput during scoping, and may recommend splitting scope or sequencing reviews if the surface area is too broad for a single contest window.<br>

#### After the contest: remediation + verification

Contest length is only one part of the timeline. Teams should also budget time for:

* Judging and deduplication: live during the contest, then finalized shortly after it ends
* Remediation: depends on number and complexity of confirmed findings
* Fix verification: review of the patch set to confirm issues are fully resolved and no new risk was introduced



#### Follow-up review windows

Sometimes the patch set is large enough that a short follow-up review is the safer move. This is common for major upgrades or when remediation touches core accounting, permissions, or integrations.<br>

In these cases, Sherlock typically recommends a shorter follow-up contest or targeted review window focused on the changes. The duration and cost are determined during scoping based on the change set and risk.
