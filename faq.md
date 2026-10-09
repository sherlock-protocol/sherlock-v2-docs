---
description: >-
  High-level information on Sherlock’s lifecycle security model, how our
  programs work, and how teams choose the right path from development through
  post-launch.
---

# FAQ

### What is Sherlock?

Sherlock provides lifecycle security for financial institutions and leading Web3 teams building and operating onchain systems. We audit crypto codebases across languages and execution environments, with services spanning protocols, applications, and infrastructure.

Our services include Collaborative Audits, Audit Engine, Bug Bounties, and Institutional Security programs, with Blackthorn as our premier audit track.

### What does “complete lifecycle security” mean in practice?

It means organizing security work around the life of a system, from initial development through launch and ongoing operation.

During development, security work helps identify risks in architecture, implementation, and dependencies. Before a launch or upgrade, reviews investigate vulnerabilities and assess proposed fixes. After deployment, ongoing security work addresses newly discovered vulnerabilities and changes to the system.

Findings, remediation decisions, and knowledge of the system carry forward between engagements. The services included at each stage depend on the agreed scope.

### Does Sherlock work with financial institutions?

Yes. Sherlock works with financial institutions and asset managers designing, launching, and operating onchain financial products.

These engagements consider the wider system through which capital moves, including vault infrastructure, underlying protocols, collateral, oracles, permissions, and operational processes. Sherlock provides crypto-native security expertise alongside the institution’s existing engineering, cybersecurity, and risk functions.

### What does an Institutional Security engagement include?

Institutional Security combines services into a program built around the institution’s infrastructure and operating requirements.

An engagement can include threat modeling, architecture guidance, auditing, custom monitoring, and incident preparedness. The work begins with understanding how the system is intended to operate and the dependencies or failures that could put capital at risk.

Before launch, the focus is on design, implementation, and remediation. During live operation, the program can include monitoring requirements and incident runbooks built around the system’s expected behavior.

The services, responsibilities, and deliverables are defined for each engagement.

### Do we need to purchase a full lifecycle program?

No. Teams can engage Sherlock for an individual service or combine services into a broader security program.

The appropriate scope depends on the system, its stage of development, existing security work, and the team’s requirements.

### What types of vulnerabilities does Sherlock focus on?

Reviews focus on vulnerabilities that could cause loss of funds, unauthorized actions, or failures in the system’s intended behavior.

Depending on the codebase, this can include access-control failures, accounting errors, broken invariants, reentrancy, oracle and price manipulation, transaction-ordering risks, unsafe upgrade paths, cross-chain interactions, and failures involving external dependencies.

Institutional engagements can also examine risks arising from vault configuration, collateral, permissions, and operational processes. The issues examined depend on the system and the engagement scope.

### What is a Collaborative Audit?

A Collaborative Audit is Sherlock’s private, time-boxed security review, carried out by a team selected for the codebase.

Researchers work together in a dedicated GitHub repository to understand the system, investigate potential vulnerabilities, and document validated findings. The engagement includes a process for discussing findings with the engineering team and reviewing submitted fixes before final reporting.

See the Collaborative Audits section for scoping, preparation requirements, the review process, and reporting.

### What is Blackthorn?

Blackthorn is Sherlock’s elite research team and premier audit track for high-stakes infrastructure.

The team consists of a small group of researchers who have consistently performed at the highest level within Sherlock’s network. Contact Sherlock to discuss whether Blackthorn is appropriate for the proposed scope.

### What is Audit Engine?

Audit Engine is Sherlock’s audit orchestration platform. It brings AI auditors, frontier models, and human security researchers into a coordinated review, with the participant mix determined by the engagement type.

Sherlock handles validation, deduplication, judging, and reporting. See the Audit Engine section for engagement types, workflows, and participation requirements.

### How should we choose between a Collaborative Audit and Audit Engine?

A Collaborative Audit centers on a selected team of researchers conducting a private review together, with direct discussion of findings and review of submitted fixes.

Audit Engine coordinates AI auditors, models, and, depending on the engagement type, human researchers against a defined scope.

The services can be used separately or together. Share the codebase, review objectives, and release timeline with Sherlock to determine the appropriate approach.

### What does “fix verification” mean?

Fix verification examines whether a proposed remediation addresses the underlying cause of a reported vulnerability and restores the intended system behavior.

Auditors also examine whether the change introduces a new issue in the surrounding code. The review covers the agreed remediation scope; it should not be treated as a review of unrelated changes or newly added features.

### What do we get as outputs from a review?

Outputs depend on the engagement. They generally include written findings, severity assessments, technical explanations, supporting evidence where applicable, and remediation guidance.

A Collaborative Audit report records the reviewed scope, code versions, findings, and outcomes of fix review.

Institutional programs may also include threat models, monitoring requirements, and incident runbooks, depending on the services included in the engagement.

### How does Sherlock handle post-launch security?

Bug bounty programs give independent researchers an ongoing route to report vulnerabilities in deployed systems and receive rewards for eligible findings.

Further reviews can examine upgrades, new integrations, and other changes that affect the system’s security assumptions.

Institutional programs can also include custom monitoring and incident preparedness, with monitoring focused on expected system behavior and runbooks defining how potential incidents should be handled.

The post-launch services and responsibilities are agreed for each engagement.

### Does Sherlock guarantee that a system will not be exploited?

No. Security work aims to reduce risk by identifying vulnerabilities, reviewing fixes, examining trust assumptions, and maintaining scrutiny as systems change.

A review applies to its defined scope, code versions, and assumptions. New functionality, configuration changes, external dependencies, and operational decisions can introduce risks outside that review.

### What chains and codebases can Sherlock support?

Sherlock reviews crypto protocols, applications, and infrastructure across languages and execution environments.

Researcher experience spans environments such as Solidity/EVM, Rust/Solana, and Bitcoin-adjacent systems. The team and review approach depend on the language, architecture, dependencies, and scope.

Share your repository, target environment, system documentation, and timeline with Sherlock to confirm the appropriate engagement.
