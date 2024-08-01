# Criteria for Issue Validity

This guide aims to provide clarity for both Watsons & protocols on various categories of issues that are valid under Sherlock's rules. Sherlock is exclusively focused on high and medium-severity findings, as these vulnerabilities will cause a loss of user funds and most materially damage the reputation of the protocols Sherlock seeks to protect.

**Note:** Despite these rules, we must understand that because of the complexity & subjective nature of smart contract security, there may be issues that are judged beyond the purview of this guide. However, for the vast majority of cases, this guide should suffice. Sherlock's internal judges continue to have the last word on considering any issue as valid or not.&#x20;

### **I. Table of Contents:**

* [#ii.-criteria-for-issue-severity](./#ii.-criteria-for-issue-severity "mention")
* [#iii.-some-standards-observed](./#iii.-some-standards-observed "mention")
* [#iv.-how-to-identify-a-high-issue](./#iv.-how-to-identify-a-high-issue "mention")
* [#v.-how-to-identify-a-medium-issue](./#v.-how-to-identify-a-medium-issue "mention")
* [#vi.-requirements](./#vi.-requirements "mention")
* [#vii.-list-of-issue-categories-that-are-not-considered-valid](./#vii.-list-of-issue-categories-that-are-not-considered-valid "mention")
* [#viii.-list-of-issue-categories-that-are-considered-valid](./#viii.-list-of-issue-categories-that-are-considered-valid "mention")
* [#ix.-duplication-rules](./#ix.-duplication-rules "mention")
* [#x.-best-practices](./#x.-best-practices "mention")

### **II. Criteria for Issue Severity:**

(repealed; see [#iv.-how-to-identify-a-high-issue](./#iv.-how-to-identify-a-high-issue "mention") and [#v.-how-to-identify-a-medium-issue](./#v.-how-to-identify-a-medium-issue "mention") for details)

### III. Sherlock's standards:

1. **Hierarchy of truth:** If the protocol team provides no specific information, the default rules apply (judging guidelines).

   If the protocol team provides specific information in the README or CODE COMMENTS, that information stands above all judging rules. In case of contradictions between the README and CODE COMMENTS, the README is the chosen source of truth.

   The judge can decide that CODE COMMENTS are outdated based on contextual evidence. In that case, the judging guidelines are the chosen source of truth.

   > Example: The code comments state that "a swap can never fail" even though the code is built to support failing swaps.

   The protocol team can use the README (and only the README) to define language that indicates the codebase's restrictions and/or expected functionality. Issues that break these statements, irrespective of whether the impact is low/unknown, will be assigned Medium severity. High severity will be applied only if the issue falls into the High severity category in the judging guidelines.

   > Example: The README states "Admin can only call XYZ function once" but the code allows the Admin to call XYZ function twice; this is a valid Medium

   The Sherlock Judge can use public statements up until 24h before the contest ends to override the language in the chosen source of truth.

   If rules are updated, the new rules apply only to contests that start after the date of change. Please check [criteria-changelog.md](criteria-changelog.md "mention") for information on the latest changes in the judging criteria/rules.

   **Historical decisions are not considered sources of truth.**

2. **Could Denial-of-Service (DOS), griefing, or locking of contracts count as a Medium (or High) issue?** DoS has two separate scores on which it can become an issue:
   1. The issue causes locking of funds for users for more than a week.
   2. The issue impacts the availability of time-sensitive functions (cutoff functions are not considered time-sensitive).
If at least one of these are describing the case, the issue can be a Medium. If both apply, the issue can be considered of High severity. Additional constraints related to the issue may decrease its severity accordingly. \
Griefing for gas (frontrunning a transaction to fail, even if can be done perpetually) is considered a DoS of a single block, hence only if the function is clearly time-sensitive, it can be a Medium severity issue.
3. **Low/Informational Issues**:  While Sherlock acknowledges that it would be great to include & reward low-impact/informational issues, we strongly feel that Watsons should focus on finding the most critical vulnerabilities that will potentially cause millions of dollars of losses on mainnet. Sherlock understands that it could be missing out on some potential "value add" for protocol, but it's only because the real task of finding critical vulnerabilities requires 100% of the attention of Watsons. While low/informational issues are not rewarded individually if a Watson identifies an attack vector that combines multiple lows to cause significant loss/damage that would still be categorized as a valid medium/high.
4. **Direct Protocol Owner/Admin rug pulls.** If a protocol specifically mentions the restrictions imposed on the owner/admin, issues describing an attack that results in bypassing these restrictions can be considered valid. Please note that these restrictions must be explicitly described by the protocol and will be considered case by case. \
   Admin functions are assumed to be used properly, unless a list of requirements is listed and it's incomplete or if there is no scenario where a permissioned funtion can be used properly.
5. **(External) Admin trust assumptions**:
   When a function is access restricted, only values for specific function variables mentioned in the README can be taken into account when identifying an attack path.

   If no values are provided, the (external) admin is trusted to use values that will not cause any issues.

   Note: if the attack path is possible with any possible value, it will be a valid issue.

   Exception: It will be a valid issue if the attack path is based on a value currently live on the network to which the protocol will be deployed.
6. **Discord messages or DM** screenshots are not considered sources of truth while judging an issue/escalation especially if they are conflicting with the contest README.
7. **Contract Scope:**
   1. If a contract is in contest Scope, then all its parent contracts are included by default.
   2. In case the vulnerability exists in a library and an in-scope contract uses it and is affected by this bug this is a valid issue.
   3. ﻿﻿If there is a vulnerability in a contract from the contest repository but is not included in the scope then issues related to it cannot be considered valid.
8. **Opportunity Loss** is not considered a loss of funds by Sherlock. For example, loss of functionality is not considered a loss of protocol revenue, nevertheless issues involving opportunity loss may be valid issues (for example, due to a loss of core functionality).
9. **Design decisions** are not valid issues. Even if the design is suboptimal, but doesn't imply any loss of funds, these issues are considered informational.
10. Watsons are expected to keep up to date with the contest's Discord channel as important announcements impacting judging may arise. They should keep in mind that any message the Sponsor sends will be considered a source of truth.

### IV. How to identify a high issue:

1. Definite loss of funds without (extensive) limitations of external conditions. The loss of the affected party must exceed 1% .

### V. How to identify a medium issue:

1. Causes a loss of funds but requires certain external conditions or specific states, or a loss is highly constrained. The loss of the affected party must exceed 0.01%.
2. Breaks **core** contract functionality, rendering the contract useless or leading to loss of funds of the affected party larger than 0.01%.

### VI. Requirements:

PoC is required for all issues falling into any of the following groups:
- non-obvious ones with complex vulnerabilities/attack paths
- issues for which there are non-trivial limitations/constraints on inputs, to show that the attack is possible despite those
- issues related to precision loss
- reentrancy attacks
- attacks related to the gas consumption and/or reverting message calls

Also, Watsons must outline all constraints of the issue being triggered and specify in which situations these constraints may trigger the issue.

### VII. List of Issue categories that are not considered valid:

1. **Gas optimizations:** The user/protocol ends up paying a little extra gas because of this issue.
2. **Incorrect Event values:**  Incorrectly calculated/wrong values in emitted events are not considered valid medium or high.
3. **Zero address checks:**  Check to make sure input values are not zero addresses.
4. **User input validation:** User input validation to prevent user mistakes is not considered a valid issue. However, if a user input could result in a major protocol malfunction or significant loss of funds could be a valid high. [Example(Valid)](https://github.com/sherlock-audit/2022-10-illuminate-judging/issues/47)
5.  **Admin Input/call validation:**
    1. Admin could have an incorrect call order. Example: If an Admin forgets to `setWithdrawAddress()` before calling `withdrawAll()` This is not a valid issue.
    2. An admin action can break certain assumptions about the functioning of the code. Example: Pausing a collateral causes some users to be unfairly liquidated or any other action causing loss of funds. This is not considered a valid issue.&#x20;
6. **Contract / Admin Address Blacklisting / Freezing:** If a protocol's smart contracts or admin addresses get added to a "blacklist" and the functionality of the protocol is affected by this blacklist, this is not considered a valid issue. \
   However, there could be cases where an attacker would use a blacklisted address to cause harm to a protocol functioning. [Example(Valid)](https://github.com/sherlock-audit/2022-11-opyn-judging/issues/219)
7. **Front-running initializers:** Front-running initializers where there is no irreversible damage or loss of funds & the protocol could just redeploy and initialize again is not a valid issue.
8. **User experience and design improvement issues:**  Issues that cause minor inconvenience to users where there is no material loss of funds are not considered valid. Funds are temporarily stuck and can be recovered by the administrator or owner. Also, if a submission is a design opinion/suggestion without any clear indications of loss of funds is not a valid issue.
9. **User Blacklist:** User getting blacklisted by a token/contract causing harm only to themselves is **not** a valid medium/high.
10. Issues assuming future opcode gas repricing are not considered to be of Medium/High severity. \
   **Use of call vs transfer** will be considered as a protocol design choice if there is no good reason why the call may consume more than 2300 gas without opcode repricings.
11. (repealed)
12. **EIP compliance with no integrations**: If the protocol does not have external integrations then issues related to code not fully complying with the EIP it is implementing and there are no adverse effects of this, are considered informational
13. **Users sending ETH/native tokens accidentally** just because a contract allows is **not** a valid medium/high.
14. **Loss of airdrops or liquidity fees** or any other rewards that are not part of the original protocol design is not considered a valid high/medium. [Example](https://github.com/sherlock-audit/2023-02-openq-judging/issues/323)
15. **Use of Storage gaps:** Simple contracts with one of the parent contract not implementing storage gaps are considered low/informational. \
    **Exception**: However, if the protocol design has a highly complex and branched set of contract inheritance with storage gaps inconsistently applied throughout and the submission clearly describes the necessity of storage gaps it can be considered a valid medium. [Example](https://github.com/sherlock-audit/2022-09-notional-judging/issues/64)
16. **Incorrect values in View functions** are by default considered **low**. \
    **Exception**: In case any of these incorrect values returned by the view functions are used as a part of a larger function which would result in loss of funds then it would be a valid **medium/high** depending on the impact.
17. **Chainlink round completeness** check is invalid. The new OCR does not rely on rounds for reporting.
18. In an update contest, issues from the previous contest with `wont fix` labels are not considered valid.
19. Issues found in mock contracts are not considered valid issues.&#x20;
20. **Chain re-org** and **network liveness** related issues are not considered valid.&#x20;\
    **Exception**: If an issue concerns any kind of a network admin (e.g. a sequencer), can be remedied by a smart contract modification, the protocol team considers external admins restricted and the considered network was explicitly mentioned in the contest README, it may be a valid medium. It should be assumed that any such network issues will be resolved within 7 days, if that may be possible.
21. **ERC721 unsafe mint:** In case of a protocol implementing minting/claiming of ERC721, users being unable to do so due to incorrect implementation is not a valid issue. \
    Example: [https://github.com/sherlock-audit/2023-03-teller-judging/issues/8](https://github.com/sherlock-audit/2023-03-teller-judging/issues/8)
22. **Future issues:** Issues that result out of a future integration/implementation that was not mentioned in the docs/README or because of a future change in the code (as a fix to another issue) are **not** valid issues.
23. **Non-Standard tokens:** Issues related to tokens with non-standard behaviors, such as [weird-tokens](https://github.com/d-xo/weird-erc20) are not considered valid by default unless these tokens are explicitly mentioned in the README.
24. Using Solidity versions that support **EVM opcodes that don't work** on networks on which the protocol is deployed is not a valid issue beacause one can manage compilation flags to compile for past EVM versions on newer Solidity versions.

### VIII. List of Issue categories that are considered valid:

1. **Slippage** related issues showing a definite loss of funds with a detailed explanation for the same can be considered valid **high**
2. **EIP Compliance:** For issues related to EIP compliance, the protocol & codebase must show that there are important external integrations that would require strong compliance with the EIP's implemented in the code. The EIP must be in regular use or in the **final state** for EIP implementation issues to be considered valid
3. **Identifies the core issue:** In case of issues that have a large number of duplicates, Issues that identify the core issue and show valid loss of funds should be grouped.
4. **Out of Gas:** Issues that result in Out of Gas errors either by the malicious user filling up the arrays or there is a practical call flow that results in OOG can be considered a valid **medium** or in cases of blocking all user funds forever maybe a valid **high**. 
   **Exception:** In case the array length is controlled by the trusted admin/owner or the issue describes an impractical usage of parameters to reach OOG state then these submissions would be considered as **low**.
5. **Chainlink Price Checks:** Issues related to `minAnswer` and `maxAnswer` checks on Chainlink's Price Feeds are considered medium **only** if the Watson explicitly mentions the price feeds (e.g. USDC/ETH) that require this check.

### IX. Duplication rules:

The duplication rules assume we have a "target issue", and the "potential duplicate" of that issue needs to meet the following requirements to be considered a duplicate.

1. Identify the root cause
2. Identify at least a Medium impact
3. Identify a valid attack path or vulnerability path
4. Fulfills other submission quality requirements (e.g. provides a PoC for categories that require one)

Only when the "potential duplicate" meets all three requirements will the "potential duplicate" be duplicated with the "target issue", and all duplicates will be awarded the highest severity identified among the duplicates.

Otherwise, if the "potential duplicate" doesn't meet all requirements, the "potential duplicate" will not be duplicated but could still be judged any other way (solo, a duplicate of another issue, invalid, or any other severity)

**Root cause groupings**

If the following issues appear in multiple places, even in different contracts. In that case, they may be considered to have the same root cause.

1. Issues with the same logic mistake.
   > Example: uint256 is cast to uint128 unsafely.
2. Issues with the same conceptual mistake.
   > Example: different untrusted external admins can steal funds.
3. Issues in the category
   - Slippage protection
   - Reentrancy
   - Access control
   - Front-run / sandwich ( issue A that identifies a front-run and issue B that identifies a sandwich can be duplicated )

The exception to this would be if underlying code implementations, impact, and the fixes are different, then they can be treated separately.

### X. Best practices:

1. Read the contest readme and documents thoroughly.
2. Submit issues that are considered valid according to Sherlock rules based on your discretion
3. Do not submit multiple issues in a single submission. Even if the 2 completely different issues occur on the same line, please make sure to separately submit them. \
   Below is a valid example where multiple occurrences can be combined into one issue:  [Example](https://github.com/sherlock-audit/2022-11-dodo-judging/issues/47).\
   Also, there could be multiple occurrences of an issue but they may need to be submitted separately as each occurrence need not be an obvious repetition like the `safeTransfer` example. Watsons must use their own discretion in such cases.
4. Be specific and sufficiently descriptive when describing an issue's impact. Bad: Loss of funds for the user Good: Loss of funds for users as there is no access control for the ‘withdraw’ function
5. **Do not add** unnecessarily **long code snippets** into the submission. Keep the code snippet limited to the scope of the impact, and be as descriptive as possible in the Vulnerability Detail sections.
6. Do not copy-paste issues from other contests/reports/past audits. They are extremely unlikely to be valid to the respective contest.&#x20;

This guide shall be regularly updated as more contests are judged and with evolving Smart contract security principles, the judging standards are subject to change over time.

### XI. Glossary

**Attack Path**: A sequence of steps or actions a malicious actor takes to cause losses or grief to the protocol or users and/or gain value or profit.

**Front-run**: There is operation A; if executed, it typically has no losses for anyone. If some other operation B executes before A, either in the same transaction or a separate transaction, there is a loss of some sort for either the protocol or some user(s) (it can be the same user)

**Root Cause**: The primary factor or a fundamental reason that imposes an unwanted outcome

**Sandwich**: A front-run, followed by operation C controlled by the attacker who also executed operation B. The goal of operation C is to revert the contract to its initial state.

**Vulnerability Path**: A sequence of steps showcasing how an issue causes losses or grief to the protocol or users through well-intended usage of the protocol.
