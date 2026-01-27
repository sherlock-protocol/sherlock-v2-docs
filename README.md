---
description: >-
  An overview of Sherlock, our security programs, and how these docs are
  organized so that teams can quickly find the right guidance for AI, audits,
  contests, bounties, & coverage. Updated January 2026.
---

# Introduction to Sherlock

Sherlock is a security organization built to protect onchain systems where software directly controls capital. We exist because security for these systems can’t be treated as a one-time event or a single deliverable. Protocols ship continuously, assumptions change, integrations shift, and incentives attract real adversaries. Security has to be an operating model.



### **Complete Lifecycle Security**

Sherlock’s model is complete lifecycle security: coverage across development, auditing, and post-launch operation.

**Development:** teams identify issues early and tighten assumptions while code is still changing fast.

**Auditing:** structured review programs pressure test architecture and code under adversarial conditions, then verify fixes before release.

**Post-launch**: ongoing incentives keep pressure on production systems as upgrades, integrations, and market conditions change.<br>

We built this model because one-off reviews don’t match how onchain systems are actually built and maintained. Protocols ship continuously, trust assumptions shift with upgrades and integrations, and many real failures come from changes made after a point-in-time review. Lifecycle security keeps the work connected across phases so teams don’t restart from zero each release.<br>

Compounding context is the practical benefit: a durable “security memory” of the system (intent, assumptions, known risk areas, prior findings, and the outcomes of fixes) that carries forward into the next change. That continuity reduces repeat findings, shortens remediation cycles, and makes upgrades safer because the starting point is an informed baseline, not a cold start.



### **How teams work with Sherlock**

Each program is designed to solve a different part of the security problem, and most teams combine them based on architecture complexity, timeline, and risk tolerance. The sections below explain what each program is, when to use it, and what to expect from the process and outputs.

#### **Sherlock offers six core services:**

**Sherlock AI:** An auditor-grade AI security tool used during development that reads your codebase in context, models protocol intent and trust assumptions, then runs specialist checks to find real exploit paths and write fix-ready findings as you build and ship.

**Collaborative Auditing:** A staffed audit where Sherlock assembles an engagement-specific team from our elite researcher network based on your protocol’s architecture and attack surface, then runs a coordinated review with fix verification through to release.

**Audit Contests:** A time-boxed public audit program that brings many independent, vetted researchers onto the same scope under clear rules and incentives, producing high-throughput issue discovery with structured judging, severity calibration, and a clean paper trail teams can remediate against.

**Bug Bounties:** A post-launch security program that keeps continuous pressure on production systems by paying independent researchers for valid live findings, with defined triage and remediation workflows so teams can receive, validate, patch, and communicate issues without chaos.

**Sherlock Shield:** An optional post-launch coverage program with defined terms that can reimburse eligible losses or payouts tied to covered security events, designed to sit alongside bounties and ongoing monitoring as a financial backstop (not a substitute for fixing root causes).

**Blackthorn:** A premium collaborative audit tier for the highest-stakes scopes, staffed by a small group of top-tier reviewers and run with deeper architecture scrutiny, tighter iteration loops, and hands-on fix verification for teams that can’t afford uncertainty.
