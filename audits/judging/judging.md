# Criteria for Issue Validity

This guide aims to provide clarity for both Watsons & protocols on various categories of issues that are valid under Sherlock's rules. Sherlock is exclusively focused on high and medium-severity findings, as these vulnerabilities will cause a loss of user funds and most materially damage the reputation of the protocols Sherlock seeks to protect.

**Note:** Despite these rules, we must understand that because of the complexity & subjective nature of smart contract security, there may be issues that are judged beyond the purview of this guide. However, for the vast majority of cases, this guide should suffice. Sherlock's internal judges continue to have the last word on considering any issue as valid or not.&#x20;

**Criteria for Issues:**

**Medium:** There is a viable scenario (even if unlikely) that could cause the protocol to enter a state where a material amount of funds can be lost. The attack path is possible with assumptions that either mimic on-chain conditions or reflect conditions that have a reasonable chance of becoming true in the future. The more expensive the attack is for an attacker, the less likely it will be included as a Medium (holding all other factors constant). The vulnerability must be something that is not considered an acceptable risk by a reasonable protocol team.

**High:** This vulnerability would result in a material loss of funds, and the cost of the attack is low (relative to the amount of funds lost). The attack path is possible with reasonable assumptions that mimic on-chain conditions. The vulnerability must be something that is not considered an acceptable risk by a reasonable protocol team.

***

### Some standards observed:

* **Could Denial-of-Service (DOS), griefing, or locking of contracts count as a Medium (or High) issue?** It would not count if the DOS, etc. lasts a known, finite amount of time <1 year. If it will result in funds being inaccessible for >=1 year, then it would count as a loss of funds and be eligible for a Medium or High designation. The greater the cost of the attack for an attacker, the less severe the issue becomes.
* **Low/Informational Issues**:  While Sherlock acknowledges that it would be great to include & reward low-impact/informational issues, we strongly feel that Watsons should focus on finding the most critical vulnerabilities that will potentially cause millions of dollars of losses on mainnet. Sherlock understands that it could be missing out on some potential "value add" for protocol, but it's only because the real task of finding critical vulnerabilities requires 100% of the attention of Watsons. While low/informational issues are not rewarded individually if a Watson identifies an attack vector that combines multiple low's to cause significant loss/damage that would still be categorized as a valid medium/high.
* **Direct Protocol Owner/Admin rug pulls.**  Sherlock's stance is generally that if a protocol team wants to rug their own project, there are often many avenues for doing this. It would be unrealistic for Sherlock to report all of these vectors in an audit. Sherlock's general assumption is that users of a protocol are taking a risk in trusting the core team of the protocol. However, if a protocol specifically mentions the restrictions imposed on the owner/admin issues describing an attack that results in bypassing these restrictions, they can be considered valid.  Please note that these restrictions must be explicitly described by the protocol and will be considered case by case.&#x20;
* Discord messages or DM screenshots are not considered sources of truth while judging an issue/escalation especially if they are conflicting with the contest README.

### List of Issue categories that are not considered valid:

* **Gas optimizations:** The user/protocol ends up paying a little extra gas because of this issue.
* **Incorrect Event values:**  Incorrectly calculated/wrong values in emitted events are not considered valid medium or high.
* **Zero address checks:**  Check to make sure input values are not zero addresses.
* **User input validation:** User input validation to prevent user mistakes is not considered a valid issue. However, if a user input could result in a major protocol malfunction or significant loss of funds could be a valid high. [Example(Valid)](https://github.com/sherlock-audit/2022-10-illuminate-judging/issues/47)
*   **Admin Input/call validation:**  Protocol admin is considered to be trusted in most cases, hence issues where

    1. Admin incorrectly enters an input parameter. Example: Make sure interestPerMin > 1 ether as it is an important parameter.  This is not a valid issue.
    2. Admin could have an incorrect call order. Example: If an Admin forgets to `setWithdrawAddress()` before calling `withdrawAll()` This is not a valid issue.

    While most of the admin input issues are invalid, there may be some issues where there could be a valid sanity check. [Example(Valid)](https://github.com/sherlock-audit/2022-10-mycelium-judging-new/issues/164)
* **Contract / Admin Address Blocklisting / Blacklisting / Freezing:** If a protocol's smart contracts or admin addresses get added to a "blocklist" and the functionality of the protocol is affected by this blocklist, this is not considered a valid issue. \
  However, there could be cases where an attacker would use a blocklisted address to cause harm to a protocol functioning. [Example(Valid)](https://github.com/sherlock-audit/2022-11-opyn-judging/issues/219)
* **Front-running initializers:** Front-running initializers where there is no irreversible damage or loss of funds & the protocol could just redeploy and initialize again is not a valid issue.
* **User experience and design improvement issues:**  Issues that cause minor inconvenience to users where there is no material loss of funds are not considered valid. Funds are temporarily stuck and can be recovered by the administrator or owner. Also, if a submission is a design opinion/suggestion without any clear indications of loss of funds is not a valid issue.
* **User Blacklist:** User getting blacklisted by a token/contract causing harm only to themselves is **not** a valid medium/high.
* **Use of call vs transfer** with the reasoning that the gas price may not be the same value of 2300. This will be considered as a protocol choice and would be considering this issue in the low/informational category.
* **EIP compliance with no integrations**: If the protocol does not have external integrations then issues related to code not fully complying with the EIP it is implementing and there are no adverse effects of this, is considered informational
* **Users sending ETH/native tokens accidentally** just because a contract allows is **not** a valid medium/high.
* **Loss of airdrops or liquidity fees** or any other rewards that are not part of the original protocol design is not considered a valid high/medium. [Example](https://github.com/sherlock-audit/2023-02-openq-judging/issues/323)
* **Use of Storage gaps:** Simple contracts with one of the parent contract not implementing storage gaps are considered low/informational. \
  **Exception**: However, if the protocol design has a highly complex and branched set of contract inheritance with storage gaps inconsistently applied throughout and the submission clearly describes the necessity of storage gaps it can be considered a valid medium. [Example](https://github.com/sherlock-audit/2022-09-notional-judging/issues/64)
* **Incorrect values in View functions** are by default considered **low**. \
  **Exception**: In case any of these incorrect values returned by the view functions are used as a part of a larger function which would result in loss of funds then it would be a valid **medium/high** depending on the impact.

### List of Issue categories that are considered valid:

* **Slippage** related issues showing a definite loss of funds with a detailed explanation for the same can be considered valid **high**
* **EIP Compliance:** For issues related to EIP compliance, the protocol & codebase must show that there are important external integrations that would require strong compliance with the EIP's implemented in the code.
* **Identifies the core issue:** In case of issues that have a large number of duplicates, Issues that identify the core issue and show valid loss of funds should be grouped and the others would be downgraded accordingly.
* **Out of Gas:** Issues that result in Out of Gas errors either by the malicious user filling up the arrays or there is a practical call flow that results in OOG can be considered a valid **medium** or in cases of blocking all user funds forever maybe a valid **high**. \
  **Exception:** In case the array length is controlled by the trusted admin/owner or the issue describes an impractical usage of parameters to reach OOG state then these submissions would be considered as **low**.
* **Future issues:** Issues that result out of a future integration/implementation that was not intended (mentioned in the docs/README) or because of a future change in the code (as a fix to another issue) are **not** valid issues.

### How to identify a high issue:

* Definite loss of funds without limiting external conditions.
* Breaks core contract functionality, rendering the protocol/contract useless (should not be easily replaced without loss of funds) and definitely causes significant loss of funds.
* Significant loss of funds/large profit for the attacker at a minimal cost.

### How to identify a medium issue:

* Causes a loss of funds but requires certain external conditions or specific states.
* Breaks core contract functionality, rendering the contract useless (should not be easily replaced without loss of funds) or leading to unknown potential exploits/loss of funds. Eg: Unable to remove malicious user/collateral from the contract.
* A material loss of funds, no/minimal profit for the attacker at a considerable cost

### Best practices:

* Read the contest readme and documents thoroughly.
* Submit issues that are considered valid according to Sherlock rules based on your discretion
* Do not submit multiple issues in a single submission. Even if the 2 completely different issues occur on the same line, please make sure to separately submit them. \
  Below is a valid example where multiple occurrences can be combined into one issue:  [Example](https://github.com/sherlock-audit/2022-11-dodo-judging/issues/47).\
  Also, there could be multiple occurrences of an issue but they may need to be submitted separately as each occurrence need not be an obvious repetition like the `safeTransfer` example. Watsons must use their own discretion in such cases.
* Be specific and sufficiently descriptive when describing an issue's impact. Bad: Loss of funds for the user Good: Loss of funds for users as there is no access control for the ‘withdraw’ function
* **Do not add** unnecessarily **long code snippets** into the submission. Keep the code snippet limited to the scope of the impact, and be as descriptive as possible in the Vulnerability Detail sections.
* Do not copy-paste issues from other contests/reports/past audits. They are extremely unlikely to be valid to the respective contest.&#x20;
* Provide a working POC for non-obvious issues with complex vulnerabilities. This helps both the protocol & judges in judging the issue.

This guide shall be regularly updated as more contests are judged and with evolving Smart contract security, the judging standards are subject to change over time.
