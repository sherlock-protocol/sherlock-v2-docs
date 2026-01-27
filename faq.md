---
description: >-
  High-level information on Sherlock’s lifecycle security model, how our
  programs work, and how teams choose the right path from development through
  post-launch.
---

# FAQ

**What is Sherlock?**

Sherlock is a leading Web3 security company for onchain systems where software directly controls capital. We provide complete lifecycle security across development, pre-launch review, and post-launch operation through Sherlock AI, Collaborative Audits, Audit Contests, Bug Bounties, and Sherlock Shield.



**What does “complete lifecycle security” mean in practice?**

It means security work that matches how protocols actually fail in production: invariants drift as features ship, upgrade paths introduce new trust assumptions, integrations change, and adversaries adapt. Lifecycle security applies pressure at three points:

* During development (before patterns harden),
* Before launch/upgrade (when risk concentrates),
* After launch (when incentives and integrations keep moving).<br>

**What types of vulnerabilities does Sherlock focus on?**

The work is designed to catch issues that commonly lead to loss of funds or broken protocol guarantees, including:

access control and privilege paths, accounting/invariant breaks, reentrancy and callback risk, oracle and price-manipulation surfaces, MEV and sequencing risk, upgrade and admin-key assumptions, cross-contract and cross-chain integration failures, and unsafe external dependency trust boundaries. Coverage depends on scope and program type.



**How is Sherlock AI used across the lifecycle?**

Sherlock AI is used across the lifecycle, with the highest leverage during development when code is changing fast. Teams run it continuously as they build, refactor, and ship—using it to surface exploitable patterns, clarify assumptions, and prioritize fixes. It also stays useful before launches or upgrades and after deployment to re-check changes, new integrations, and evolving attack surfaces as the system evolves.



**What is a Collaborative Audit?**

A Collaborative Audit is a staffed engagement where Sherlock assembles an engagement-specific team and runs a coordinated review for high-stakes scopes. The team builds an architecture-level understanding of the protocol, maps trust boundaries and attack surfaces, tests exploit paths, and verifies fixes through iteration. It’s the right fit when complexity, upgradeability, or integration risk calls for tight feedback loops and hands-on fix validation.



**What is Blackthorn?**

Blackthorn is Sherlock’s elite collaborative audit program for the highest-stakes scopes. It’s a staffed engagement led by a small group of top-tier reviewers who go deep on architecture, threat modeling, and exploit-path analysis, then stay engaged through iteration to verify fixes. Teams use Blackthorn when a standard review cadence isn’t enough: new primitives, complex integrations, large TVL, or launch timelines where uncertainty is the real risk.



**What is an Audit Contest?**

An Audit Contest is a public review program where many independent security researchers analyze the scope concurrently under clear incentives. The focus is breadth and throughput: multiple independent perspectives, many parallel lines of inquiry, and fast coverage of attack surfaces that can be missed by a small team.



**How should we choose between a Collaborative Audit and an Audit Contest?**

Teams typically choose a Collaborative Audit when they need coordinated depth on architecture, invariants, roles, and integrations, plus an iterative fix-and-verify loop with a staffed team. Choose an Audit Contest when you want maximum parallel coverage from independent researchers and high throughput on a clearly defined scope. Many teams combine them: Collaborative Audit first to pressure test the design and verify fixes, then a Contest to add breadth on the hardened release candidate.



**What does “fix verification” mean?**

Fix verification is the step where proposed remediations are reviewed against the reported exploit path and the protocol’s intended invariants. The goal is to confirm the fix closes the specific failure mode without introducing regressions or new trust assumptions.



**What do we get as outputs from a review?**

Outputs vary by program, but generally include written findings and severity assessments, proof-of-concept or exploit reasoning where applicable, reproduction context, and guidance on remediation. For pre-launch programs, the emphasis is on actionable results: what breaks, why it breaks, and what changes are required to restore intended guarantees.



**How does Sherlock handle post-launch security?**

Post-launch security is driven by incentive programs like bug bounties, which keep ongoing pressure on production systems. This is meant to match reality: upgrades, parameter changes, new integrations, and market conditions change the effective threat model over time, so scrutiny has to persist after deployment.



**What is Sherlock Shield?**

Sherlock Shield is optional financial coverage that can sit alongside post-launch programs under defined terms. Coverage availability, eligibility, scope, and limits depend on the program terms and the details of the reviewed system.



**Does Sherlock guarantee the protocol won’t be exploited?**

No. The goal is to materially reduce risk by identifying and fixing vulnerabilities, clarifying trust assumptions, validating invariants, and maintaining scrutiny as the system evolves. Outcomes depend on scope definition, code maturity, change cadence, operational controls, and integration complexity.



**What chains and codebases can Sherlock support?**

Sherlock supports smart contract security work across major onchain environments, and the recommended program depends on your stack and architecture (for example EVM Solidity vs Solana Rust), the deployment model (upgradeable vs immutable), and how much integration surface area exists. If you share your target chain, repo, and timeline, the right program mix becomes straightforward to recommend.

<br>
