---
description: >-
  How to read Sherlock AI run output, validate assumptions and exploit paths,
  triage issues as valid or invalid, and close findings with fixes and re-runs.
---

# Understanding Sherlock AI results

Every Sherlock AI run is tied to a specific snapshot of your code. When you open a run, you’re reviewing findings generated against a particular branch/commit and the assumptions the analysis used to reason across the repository. Treat the run like an audit artifact: it should map cleanly to a PR, a patched commit, and a follow-up re-run.

<figure><img src="../.gitbook/assets/Screenshot 2026-01-29 at 3.37.59 PM.png" alt=""><figcaption></figcaption></figure>

### Run summary

At the top of the run you’ll see the run identifier, status, timestamp, and branch. You’ll also see two counters that matter for triage:



#### **Assumptions made**

These are explicit assumptions Sherlock AI relied on to model behavior across the system. They often relate to integration reality (external contract interfaces, token behavior), configuration (addresses wired in, upgrade state), and trust boundaries (which roles are expected to be trusted). Assumptions act like dependencies for findings: if a finding depends on an assumption that doesn’t hold in your deployment, the path may be irrelevant or the mismatch may itself be a risk you should address.

#### **Issues found**

The number of issues produced for the run, grouped by severity. Severity is a prioritization signal. Before treating severity as release-blocking, confirm reachability and exploit preconditions against your actual deployment model.<br>

### Issues list and navigation

The left panel is an index of issues grouped by severity (for example, High and Low). Titles are written to be grep-able: they typically name the component/function and the failure mode. Use search and filters to work through a run the same way you’d work through a formal report: start with High severity issues, then move down, or focus on the subsystem you’re actively changing.



### Anatomy of an issue

Each issue is structured to help you validate quickly and fix deterministically.

**Title / summary**

A direct statement of what breaks and where. Good issue titles usually include the relevant module/function and the failure mode (for example, DoS via a revert, privilege escalation, accounting drift, or integration mismatch).

**Severity**

Shown near the top of the issue. Severity is based on expected impact if the path is reachable under stated assumptions. It is not a substitute for checking access control, state constraints, and integration reality.

**Valid issue / Invalid issue**

These controls are how you record triage decisions.

Mark Valid when you’ve confirmed the path is reachable in your environment and the behavior violates your security model.

Mark Invalid when the report depends on assumptions that don’t hold, misinterprets intended behavior, or describes a path blocked by constraints that are actually enforced (role gating, state invariants, configuration, interface guarantees you control).d

If you mark an issue Invalid, leave a short technical reason in your internal tracking (or link a note/PR discussion) so the decision remains auditable later.



### Core sections you’ll see in findings

Most issues follow a consistent structure:<br>

**Explanation**

A mechanical description of why the issue exists. This should identify what the code assumes, what boundary is being crossed, or what invariant is being violated. When you’re validating, look for the exact dependency: “this external contract must implement method X,” “this role must be untrusted,” “this state transition is reachable,” etc.

**Attack Path**

A step-by-step call sequence that shows how the failure occurs. This is the fastest way to validate. Walk the path against the code snapshot and check preconditions:

* Who can call the entry point?
* Under what state is the path reachable?
* What inputs are required?
* What external contracts/interfaces must behave a certain way?

If you can’t make the path work on paper against your code and deployment constraints, the issue is likely invalid or dependent on a wrong assumption.

**Impact**

What breaks if the path triggers: denial of service on a critical operation, incorrect accounting, privilege escalation, stuck funds, or value loss. Use impact to decide urgency and ownership (core protocol engineers, integration owners, or infra).

**Suggested Fix**

A fix direction written for engineers, sometimes including a minimal code change. Treat this as a patch hypothesis, not an instruction. The right close-out is always: implement the fix in a PR, ensure tests cover the failure mode, then re-run Sherlock AI against the patched commit.



A good triage loop is consistent and repeatable:

**Start with assumptions**

Identify which assumptions the issue depends on and confirm they match your intended deployment. A large portion of “looks scary” findings become straightforward once the underlying assumption is confirmed or corrected.



**Confirm reachability**

Verify the entry point is callable by an attacker class you care about (public user, privileged role, external system) and that state conditions needed for the path can actually occur.<br>

**Confirm the failure mode**

Find the line(s) where behavior breaks: the revert reason, arithmetic behavior, storage write, call result, or state invariant violation. You want the concrete “this is the moment it fails,” not just a narrative.<br>

**Decide disposition**

Mark Valid or Invalid. If Valid, decide whether it blocks the release or can be scheduled.<br>

**Patch and re-run**

After remediation, re-run Sherlock AI on the new commit. The run is your regression check: it confirms the exploit path is closed on the code you actually plan to ship.



Severity helps you prioritize, but it isn’t magic. Two technical checks matter more than the label:

* Reachability: the path must be callable under real constraints.
* Impact domain: what the path enables if it triggers (DoS vs value loss vs privilege).<br>

High severity findings are often “integration-real”: they become critical only when a particular external contract or configuration is used in production. That’s why the assumptions counter exists. If the assumption is correct, treat the issue with urgency. If the assumption is wrong, treat it as a signal to tighten configuration validation or integration guards.



### Closing out a run

A run is in good shape when:

* High severity issues are either patched or explicitly accepted with clear reasoning.
* Fixes are tied to PRs/commits, not vague statements.
* A follow-up run on the patched commit shows the exploit paths are no longer present.<br>

Sherlock AI is strongest when you use results this way: as a structured set of testable claims tied to a commit, with a workflow that turns each valid issue into a verified patch.
