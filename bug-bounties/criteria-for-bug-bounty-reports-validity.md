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
