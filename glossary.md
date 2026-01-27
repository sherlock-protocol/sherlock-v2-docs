# Glossary

#### People and roles <a href="#docs-internal-guid-81ee12bc-7fff-da7c-d48e-f1356acb8e78" id="docs-internal-guid-81ee12bc-7fff-da7c-d48e-f1356acb8e78"></a>

**Protocol team:** The builders and operators of the system in scope. Typically includes engineering, security, and operations roles responsible for scoping, remediation, and deployment decisions.

**Security researcher:** An independent researcher who analyzes code and systems to find vulnerabilities and reports them through a contest or bounty under the program rules.

**Watson:** A security researcher participating in Sherlock programs. Watsons submit findings in contests and bounties and are incentivized to surface real exploit paths and concrete impact.

**Judge:** The party responsible for evaluating contest submissions under the published rules. Judges validate issues, assign severity, group duplicates, and determine the final results.

**Judging:** The end-to-end evaluation process for contest submissions: validation, impact and exploitability assessment, severity assignment, duplicate grouping, and final outcome determination based on contest rules.

***

#### Core concepts

**Finding (Issue):** A security-relevant problem identified in code, configuration, or system design. A finding typically includes an impact statement, an attack path (or failure mode), and remediation guidance.

**Severity:** A classification of a finding based on impact and exploitability. Severity reflects what can break (loss of funds, unauthorized control, insolvency, denial of service, invariant violation) and how realistically an attacker can reach that state given prerequisites and constraints.

**Impact:** What a finding enables if exploited: fund loss, permission escalation, governance/control takeover, bad debt, broken accounting, state corruption, or other defined adverse outcomes.

**Exploitability:** How feasible it is to turn a finding into a real attack path. Exploitability depends on prerequisites (roles/keys), reachable call paths, external dependencies (oracles, integrations), economic conditions, and timing/sequencing constraints.

**Proof of Concept (PoC) / Reproduction:** Evidence that a finding is real and reachable. This can be a test case, transaction sequence, minimal exploit script, or a clear set of steps that reproduces the behavior.

**Scope:** The exact system boundary covered by a program: repositories, commit hashes/tags, deployed addresses, specific contracts/programs, and explicitly included integrations. Scope defines what is reviewed and what results are expected to apply to.

**In scope / Out of scope:** In scope means the issue affects components and versions included in the defined boundary. Out of scope means the issue involves excluded components, unsupported versions, or threat models the program explicitly does not cover.

**Release candidate (Scope freeze):** A pinned version of the code intended for deployment (or already deployed) that the review applies to. This is usually a commit hash, tag, or set of deployed addresses. Changes after the freeze are not automatically covered unless explicitly re-reviewed.

**Fix verification (Retest):** A follow-up review that checks whether a remediation closes the reported failure mode and does not introduce regressions or new trust assumptions. Verification may include reviewing the patch and re-evaluating exploit paths against the updated code.

**Disclosure:** The process of reporting a vulnerability through an agreed channel so it can be validated and fixed before details are shared publicly. Disclosure expectations are defined by the rules of the program (contest or bounty) and any safe-harbor terms.

***

#### Development

**Sherlock AI:** Auditor-grade analysis used across the lifecycle, with the highest leverage while code is still changing. Teams use it during development to surface likely vulnerabilities, clarify trust assumptions, and prioritize fixes as they build and refactor.

**AI finding:** A potential issue flagged during development-time analysis. AI findings still require engineering validation; teams confirm reachability, impact, and whether the behavior matches protocol intent.

**Assumptions:** Explicit or implicit statements the system relies on to be safe (roles cannot be compromised, oracle inputs behave within bounds, integrations meet certain guarantees, invariants hold under all user actions). Many high-severity failures come from assumptions that were never written down or drifted over time.

***

#### Auditing (Pre-launch review)

**Collaborative Audit:** A staffed, coordinated review for high-stakes scopes. The emphasis is depth: architecture understanding, adversarial reasoning, and fix verification with a tight feedback loop.

**Audit report:** A written artifact that documents findings, severity, reproduction context, and remediation guidance for an agreed scope and version.

**Audit Contest:** A structured public review program where many independent researchers analyze a defined scope concurrently under clear incentives, rules, and timelines. The emphasis is breadth and throughput.

**Contest submission:** A report submitted by a Watson during a contest. Submissions are evaluated for validity, severity, and scope alignment.

**Duplicate:** A submission that describes the same underlying issue as another submission. Contest rules determine how duplicates are handled and how credit is assigned.

**Contest rules:** The published constraints and evaluation criteria for a contest, including scope definition, submission requirements, severity definitions, duplicate handling, and payout methodology.

**Contest results:** The finalized set of validated findings after judging, including severity assignments, duplicate groupings, and any final notes required by the rules.

***

#### Post-Launch protection

**Bug bounty:** An ongoing post-launch program that rewards responsible disclosure of vulnerabilities in a live system. Bounties exist to keep pressure on production deployments as upgrades, integrations, and market conditions change.

**Bounty submission:** A report describing a vulnerability or exploit path in a live system under an active bounty program. Submissions are triaged for validity, severity, and scope alignment.

**Triage:** The process of validating a report, reproducing the behavior, assessing impact and exploitability, assigning severity, and coordinating remediation.

**Safe harbor:** Terms that define permitted testing behavior and disclosure expectations for researchers acting in good faith. Safe-harbor language is typically program-specific.

***

#### Sherlock Shield

**Sherlock Shield:** Optional financial coverage that can sit alongside post-launch programs under defined terms.

**Coverage:** A defined limit and set of terms describing what reimbursements may be available under Shield. Coverage is bounded by scope, eligibility requirements, and exclusions.

**Claim:** A formal request submitted under Shield terms when an event occurs that may be eligible for reimbursement. Claims are evaluated against scope, evidence, and exclusions.

**Premium:** The amount paid for Shield coverage over a defined time period, based on the agreed limits, scope, and risk profile.

**Exclusions:** Events, failure modes, or components explicitly not covered under Shield terms. Exclusions define boundaries and prevent ambiguity around eligibility.

<br>
