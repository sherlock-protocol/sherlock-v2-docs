---
description: >-
  This page includes the standards, duplication clarifications and general out
  of scope issues general for all Bug Bounty programs.
---

# Criteria for Bug Bounty reports validity

#### I. Sherlock's standards:

1.  If the protocol team includes specific information in the Bug Bounty Page or Code Comments, that information may be used as context during the triaging process. In cases where there is a contradiction between the Bug Bounty Page and Code Comments, the Bug Bounty Page should be considered the primary source of truth.

    The judge can decide that Code Comments are outdated. In that case, the default guidelines apply.

    > Example: The code comments state that "a swap can never fail" even though the code is built to support failing swaps.
2. The report should include one vulnerability, and if the submitter identifies several vulnerabilities, they should be submitted separately.
3. **(External) Admin trust assumptions**:\
   Admin functions are generally assumed to be used correctly and not harm users/the protocol, unless the protocol provides specific trust assumptions/restrictions in the Bug Bounty Page.
4. **Contract Scope:**
   1. If a contract is in Bug Bounty Scope, then all its parent contracts are included by default.
   2. In case the vulnerability exists in a library and an in-scope contract uses it and is affected by this bug this is a valid issue.
   3. If there is a vulnerability in a contract that is not included in the scope then issues related to it cannot be considered valid.
5. **Low vs Informational** (smart contracts and web2 alike):
   1. **Low** means the issue works: against the current code or deployment, you can show real (even if small) harm to the protocol or to someone other than yourself.
   2. **Informational** means there is no harm you can show today: hardening ideas, best-practice gaps, configuration opinions, code quality, design choices (II.22), and issues that only matter if something else changes first (II.18).
   3. The test: does a working PoC hurt someone other than you? If yes but the harm is small, it's Low. If no, it's Informational, however sensible the advice.

      > Example: a missing `X-Frame-Options` header on its own is Informational. Framing the page to trick a logged-in user into changing a setting, shown with a working PoC, is at least Low.
   4. Informational reports are not rewarded unless the Bug Bounty Page says otherwise. Each Bug Bounty Page sets whether Lows are rewarded, and how much.

#### II. List of Issue categories that are not considered valid:

1. **Gas optimizations:** The user/protocol ends up paying a little extra gas because of this issue.
2. **Incorrectly calculated/wrong values in emitted events** are not considered a valid issue.
3. Check to make sure input values are not zero addresses are **not** considered valid issues.
4. **User input validation to prevent user mistakes** is not considered a valid issue. However, if a user input could result in a major protocol malfunction or significant loss of funds for other parties (protocol or other users) and it qualifies for in-scope severity definitions, then it can be valid.
5. **Admin Input/call validation:**
   1. Admin could have an incorrect call order. Example: If an Admin forgets to `setWithdrawAddress()` before calling `withdrawAll()` This is not a valid issue.
   2. An admin action can break certain assumptions about the functioning of the code. Example: Pausing a collateral causes some users to be unfairly liquidated or any other action causing loss of funds. This is not considered a valid issue.
6. **If a protocol's smart contracts or admin addresses get added to a "blacklist"** and the functionality of the protocol is affected by this blacklist, this is not considered a valid issue.
7. **Front-running initializers** where there is no irreversible damage or loss of funds & the protocol could just redeploy and initialize again is not a valid issue.
8. Issues causing only **minor user experience issues inconvenience** without fund loss, such as temporarily inaccessible funds recoverable by the admin, are not valid.
9. **User getting blacklisted** by a token/contract causing **harm only to themselves** is **not** a valid issue.\
   However, if the malicious actor can use a blacklisted address and harm other parties (protocol or other users), and it qualifies for in- scope severity definitions, then it can be considered valid.
10. Issues assuming future opcode gas repricing are not considered to be valid issues.\
    **Use of call vs transfer** will be considered as a protocol design choice if there is no good reason why the call may consume more than 2300 gas without opcode repricings.
11. **Users accidentally or intentionally directly transferring any tokens** (native, ERC20, etc.) into the in-scope contracts, while it is not a part of the expected protocol operations, and the contract doesn't have a way to retrieve them, is **not** a valid issue and is considered a user mistake, if the user hurts themselves only. However, if it leads to hurting the protocol and/or other users, it may be considered a valid issue (if qualifies for in-scope severity definitions).
12. **Loss of airdrops** or any other rewards that are not part of the original protocol design is not considered a valid issue.
13. **Incorrect values in View functions** are by default considered **invalid**.\
    **Exception**: In case any of these incorrect values returned by the view functions are used as a part of a larger function which would result in loss of funds then it can be considered valid if it qualifies for in-scope severity definitions.
14. **Stale prices and Chainlink round completeness** Recommendations to implement round completeness or stale price checks for any oracle are invalid.

    > Exception: the recommendation to implement stale price checks **may** be valid. For [example](https://github.com/sherlock-audit/2024-12-mach-finance-judging/issues/41), the protocol may be using Pyth pull-based oracle, which requires requesting the price before using it. Hence, if we don't request the price firstly, or check it for staleness, then we can end up using very old price (e.g. from 1 hour/day ago).
15. Issues from the previous audits (linked in the Bug Bounty Page) marked as acknowledged (not fixed) are not considered valid.
16. **Chain re-org** and **network liveness** issues are not valid. However, if the underlying protocol is blockchain and the malicious actor can force a chain re-org affecting the protocol and the users, it can be a valid issue if it qualifies for in-scope severity definitions.
17. Issues where users cannot safemint ERC721 tokens due to unsupported implementation are not valid.
18. **Future issues:** Issues that result out of a future integration/implementation that was not mentioned in the docs/README or because of a future change in the code (as a fix to another issue) are **not** valid issues.
19. Issues related to **tokens with non-standard behaviors**, such as [weird-tokens](https://github.com/d-xo/weird-erc20) are not considered valid by default unless these tokens are explicitly mentioned in the Bug Bounty Page. Tokens with decimals between 6 and 18 are not considered weird.
20. Using Solidity versions that support **EVM opcodes that don't work** on networks on which the protocol is deployed is not a valid issue beacause one can manage compilation flags to compile for past EVM versions on newer Solidity versions.
21. **Sequencers** are assumed to operate reliably without misbehavior or downtime. Vulnerabilities or attacks that rely on sequencers going offline or malfunctioning are invalid.
22. **Design decisions** are not valid issues. Even if the design is suboptimal, but doesn't imply any loss of funds, these issues are considered informational.
23. **Lack of storage gaps** in parent contracts are not considered valid issues.

#### III. Duplications:

If the report is a duplicate of a previously submitted report, then it won't be rewarded even if the issue hasn't been fixed prior to the subsequent submissions. The timestamp of the submission will be used to decide which report was submitted earlier.

The duplication of the issue will be considered based on the **root cause** of the reported issue. Therefore, if the reported issues have the same root cause or address the same vulnerability, but appear in multiple places, even in different contract, they may be considered to have the same root cause and considered duplicates.

#### IV. Best Practices

1. Read the Bug Bounty page and documents thoroughly.
2. Submit issues that are considered valid according to Sherlock guidelines based on your discretion.
3. Be specific and sufficiently descriptive when describing an issue's impact. Bad: Loss of funds for the user Good: Loss of funds for users as there is no access control for the ‘withdraw’ function
4. **Do not add** unnecessarily **long code snippets** into the submission. Keep the code snippet limited to the scope of the impact, and be as descriptive as possible in the Vulnerability Detail sections.
5. Do not copy-paste issues from other contests/reports/past audits. They are extremely unlikely to be valid to the respective contest.

#### V. Web2 and off-chain assets

Sherlock runs bug bounties for web2 and off-chain assets as well as smart contracts. That covers websites and web apps, APIs and backends, SDKs, front ends and infrastructure. Each program's Bug Bounty Page decides which assets are in scope and how severities and rewards work. The guidelines below apply wherever the page doesn't say otherwise.

The general rules on this page also apply to web2 reports: one vulnerability per report, admin trust assumptions, design decisions, future issues, known issues, Low vs Informational, and duplicates judged by root cause.

**1. Scope**

1. Only the domains, apps, API endpoints, SDKs and repositories listed on the Bug Bounty Page are in scope. A subdomain is in scope only if it is listed or covered by a wildcard (e.g. `*.example.com`).
2. Third-party services the program relies on are not in scope, even when a bug in them affects the program. This includes hosting, CDNs, wallets and wallet extensions, sign-in providers, analytics and RPC providers. Report those to their owners. However, how the program team has set these services up is in scope. Example: a DNS record still pointing to a hosting account the team no longer owns.
3. For SDKs and libraries, impact is judged on the program's own apps and on integrators who use the SDK as documented. Using an SDK against its documentation is a user mistake (see II.4).

**2. Severity**

Severity follows the impact you show, not the type of bug. The same XSS can be Critical on a page where users sign transactions and Low on a static page. Severity goes down when the attack needs a privileged account, a lot of action from the victim, or unlikely conditions.

| Severity | What it means | Typical impacts |
| --- | --- | --- |
| **Critical** | Full compromise of the system, of user funds, or of what users sign, with little or no action from the victim | Running arbitrary code or commands on a server. Reading live secrets that control systems or funds (signing keys, database or cloud credentials). Changing what users sign or where their funds go (recipient, amount, approval, contract address) through the app, an API response or the SDK. Changing the code or content served to all users (through DNS, a CDN, CI/CD or a published package). Gaining admin access, or taking over any account without the victim doing anything. Theft of user funds. Access to sensitive data of all or most users. |
| **High** | Serious harm to other users or the program, needing at most limited action from the victim (e.g. one click) | Taking over a regular user's account with one click or less (e.g. stored XSS, session theft). Reading or changing other users' sensitive data: email, phone, address, KYC documents, API keys, login details. Reaching internal services or admin interfaces that should be closed (e.g. SSRF, broken access control). Taking over a subdomain users trust. Content injection that other users see and that persists (stored HTML injection, malicious file uploads). Taking an in-scope app or API offline for all users through a bug, not through traffic volume. |
| **Medium** | Limited harm, usually needing victim interaction or specific conditions | Changing other users' non-sensitive settings with one click (e.g. CSRF on a display name or notification settings). Reflected HTML injection. Open redirects to attacker-controlled sites. Exposing other users' non-sensitive data. Breaking a non-critical feature for other users. Bypassing business rules for limited gain (e.g. claiming a referral reward twice). |
| **Low** | Real but small harm to others, needing significant victim interaction or unlikely conditions | Attacks on other users that need several unusual steps from the victim. Temporarily locking a specific user out (forced login lockouts, cookie bombing). Taking over a broken outbound link or abandoned social account that the app links to. |

For where Low ends and Informational begins, see I.5.

**3. Common out-of-scope issues**

Unless the Bug Bounty Page says otherwise, these are not considered valid:

1. Theoretical issues with no working PoC, and scanner output submitted without proof of impact.
2. Missing security headers or cookie flags (`HttpOnly`, `Secure`, `SameSite`), or CSP and SSL/TLS configuration choices, unless you show a working exploit through them.
3. Missing or weak email authentication records (SPF, DKIM, DMARC).
4. Self-XSS and anything else that only affects the person doing it, including attacks that need the victim to paste code into their browser.
5. Clickjacking on pages with no sensitive action. CSRF on actions with no security impact (e.g. logout).
6. Missing rate limits, brute force and captcha bypasses. **However**, if you show a concrete impact on a sensitive action (e.g. guessing a one-time login code), it can be valid.
7. Denial of service that relies on traffic volume (DDoS).
8. Social engineering and phishing, and attacks that need physical access, the victim's device or their local network.
9. User or email enumeration with no further impact.
10. Verbose error messages, stack traces, version banners, IP addresses and server names.
11. Outdated libraries or known CVEs, unless you show the vulnerable code is reachable and exploitable in the program's assets.
12. Content spoofing or text injection with no HTML or script.
13. Tabnabbing, and issues that need an outdated browser, a browser bug or a malicious browser extension.
14. Public client-side keys that are meant to be shared (e.g. RPC, analytics or map keys), and secrets in public code that are no longer live.
15. Access to data or resources that are public by design.
16. UI/UX bugs and best-practice suggestions with no security impact.
17. Attacks that need stolen credentials, a compromised device, or access the attacker shouldn't already have.

**4. Testing and proof of concept**

These apply on top of the [Platform Rules](post-launch-bounty/platform-rules.md):

1. Every web2 report needs a working PoC. Include the exact steps, the requests and responses (or a script), and screenshots or a short video that show the impact. Keep everything in the report itself.
2. Use your own accounts. To show one user affecting another, create a second account and use it as the victim. Never access, change or delete real users' data or funds.
3. Prefer a local or test setup: run the open-source front end or SDK locally, or use the program's staging environment if it has one. Test production only as far as you need to prove the issue, and stop there.
4. Prove the issue, don't exploit it:
   - Show one record from your own test account, not a data dump.
   - Run one harmless command (e.g. `whoami`). Don't move further into the system or keep access.
   - Never send transactions that affect other users or the protocol's funds.
5. If you reach real users' data by accident, stop. Don't keep, copy or share it, and say in the report what you saw.
6. If you find leaked keys or credentials, report them. Don't use them.
7. No denial-of-service testing against live systems, no high-volume automated scanning, and no social engineering or phishing of the team or its users. Show resource-exhaustion issues locally, or explain them.
8. Remove test content you created where you can, and list anything you couldn't remove.

Breaking these rules can get the report invalidated and lead to removal from the platform, as set out in the Platform Rules.
