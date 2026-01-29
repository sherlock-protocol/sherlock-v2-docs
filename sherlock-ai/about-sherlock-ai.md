---
description: >-
  What Sherlock AI is, how it analyzes repositories in context, and what teams
  use it for during development and pre-launch review.
---

# About Sherlock AI

Sherlock AI is an auditor-grade AI security system for onchain code. Teams use it during development and pre-launch review to surface exploit paths earlier, tighten assumptions, and produce fix-ready findings while code is still changing.

Sherlock AI is built for real repositories, not isolated snippets. It reads the codebase in context, forms a working model of intended behavior and trust boundaries, then runs targeted analysis paths that map to common exploit surfaces (permissions, value flow, external calls, upgrades, invariants). The output is written for engineers: what breaks, how it can be abused, and what to change.

### How it works

Sherlock AI runs analysis as a job-based workflow. Requests are submitted, queued, and processed asynchronously so teams can run audits without blocking on execution time, and so larger orgs can run scans across many repos with consistent tracking.&#x20;

Each job moves through a deterministic, stage-based pipeline designed to reduce variance and produce structured intermediate artifacts that roll up into final findings.

A typical run follows five stages:&#x20;

1. **Plan** — identify scope, language, and relevant files
2. **Research** — build a structured view of the codebase and generate hypotheses
3. **Validate** — test and refine hypotheses against the code and context
4. **Judge** — apply stricter criteria to confirm or reject findings
5. **Report** — produce final issue reports and emit lifecycle events

### What you get

Sherlock AI produces structured findings that are meant to be fixed, tracked, and reviewed:

* Clear issue statements tied to concrete exploit paths
* Supporting evidence and traceability back to the relevant code
* Outputs that can feed into review workflows and dashboards via lifecycle events (and optional webhook-style integrations, where configured)&#x20;

### Where teams use it

Sherlock AI is commonly used in three moments:

* During development, as code changes daily
* As a readiness pass before a staffed audit or contest
* Across many repositories for periodic security sweeps and regression checking&#x20;

### What to expect

Sherlock AI is designed to reduce late-stage surprises by turning “we think this might break” into a concrete, fix-ready security report while there is still time to act. It does not replace human review for high-stakes releases; it changes the baseline teams bring into that review.
