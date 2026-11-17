# Platform Rules

In order to facilitate cordial and productive exchanges between protocol customers and whitehats, Sherlock has established a set of rules for whitehats and protocol customers to define proper conduct.&#x20;

Breaking these rules as a whitehat could result in removal or ban from the Sherlock platform and/or withholding of payout.&#x20;

Breaking these rules as a protocol team could result in removal from the Sherlock platform and/or provide cause for breakage of the mutually signed agreement.&#x20;

Each program's page can add its own rules on top of these. Where they differ, the program page wins.

### Whitehats

#### Ethical Standards

* Adhere to ethical standards and legal guidelines. Any actions that compromise the integrity, privacy, or availability of systems beyond what is necessary for testing are strictly prohibited.
* No harm: Ensure that your testing does not negatively impact users or infrastructure.
* Always default to the assumption that the protocol team has good intentions.
* Do not threaten, blackmail, dox, or otherwise create a negative environment for the protocol customer.
* Do not communicate with the protocol customer outside of the official channel provided by Sherlock (see [Communication](#communication)).
* By submitting a vulnerability through Sherlock, you are agreeing to abide by the outcome of the Sherlock dispute resolution process

#### Report Requirements

Your report must be complete on its own. We judge only what you submit, as it was at the time you submitted it. Each report needs:

1. **Title:** the bug and its impact in one line.
2. **Summary:** what's wrong, in a few sentences.
3. **Affected code:** the contract or file and function, with line numbers at the program's in-scope commit (or the deployed address).
4. **Root cause:** why the code behaves this way.
5. **Impact:** which severity category on the program page it meets, and why, with numbers (funds at risk, duration, who is affected).
6. **Proof of concept:** runnable code pasted into the report as a code block, with the command to run it and the output you got. Run it against a local fork or test deployment, never against live systems.
7. **Recommended fix** (optional).

One vulnerability per report.

Links to gists, repositories, documents or videos can add detail, but they don't replace the report. **A report that is only a link, or that leaves required sections to an external page, is invalid.** Content added or changed outside the submission after you submit (an edited gist, for example) isn't considered.

#### Submission Deposit

Most programs ask for a deposit with each report: 250 USDC by default, paid in **native USDC on Polygon** (contract `0x3c499c542cEF5E3811e1192ce70d8cC03d5c3359`). Other tokens (such as USDC.e) and other networks aren't detected. The deposit for each severity is shown on the submission form, next to each severity, once you start a report. Some programs don't charge a deposit for every severity. What happens to a deposit depends on the report's outcome and on who triaged it.

#### Deposit Refunds

Most reports are triaged by Sherlock. If Sherlock triages your report, your deposit is refunded once the report is closed, unless the report is spam, AI-generated or clearly out of scope.

Some reports are reviewed by an outside expert triager from Sherlock's researcher community, and on those externally judged submissions the deposit pays the triager for their time. If an externally judged report is valid, the deposit still goes to the triager, but you can receive a credit for it to use on a future submission.

**How refunds are paid.** Refunds are paid in native USDC on Polygon.

**Sent on the wrong network or token?** The deposit isn't detected and the report isn't submitted. Open a ticket in the [Sherlock Discord](https://discord.com/invite/MABEWyASkp) with the transaction hash.

**Deposit not refunded?** If your deposit wasn't refunded and you believe it should have been, open a ticket in the [Sherlock Discord](https://discord.com/invite/MABEWyASkp) with your submission ID or the report's title.

#### Communication

* **Replies about your report:** reply to the emails we send you about your submission, from the same email address you submitted with. Your reply is added to the submission's conversation, where Sherlock and the protocol team see it. Emails from any other address aren't received, and attachments don't come through: paste text and code into the email body.
* **No response after a week:** reply to the confirmation email you got when you submitted your report to escalate to Sherlock. If that gets no answer either, open a ticket in the [Sherlock Discord](https://discord.com/invite/MABEWyASkp) with your submission ID or the report's title.
* **Anything else** (deposits, refunds, account questions): open a ticket in the [Sherlock Discord](https://discord.com/invite/MABEWyASkp).

#### Testing Environment

* Replicating tests on public mainnet or testnet is prohibited. All testing should be conducted on local forks of either testnet or mainnet.
* Use only authorized environments for testing to avoid any unintended disruptions or security risks.
* Avoid testing with external dependencies and third-party systems not controlled by the protocol customer to avoid any leaks of the potential vulnerability
* **Web2 and off-chain assets** (websites, apps, APIs, backends) can't be tested on a fork. Use your own accounts, keep requests to the minimum needed to prove the issue, and never access, change or delete other users' data. The web2 testing rules on the [criteria page](../criteria-for-bug-bounty-reports-validity.md) (section V) apply.

#### Service Disruptions

* Any denial of service attacks that are executed against project assets are strictly forbidden.
* Automated testing of services that generates significant amounts of traffic is not permitted.

#### Vulnerability Disclosure

* Do not disclose or discuss a submitted vulnerability, publicly or privately, until the protocol team has confirmed it's fixed and given you explicit permission. Disclosure is the protocol team's decision.
* Report via Sherlock: Use the official reporting channels to submit your findings.
* Never exploit a vulnerability or threaten to do so
* Do not attempt to rescue funds without the written consent of the protocol customer
* Known issues, including bugs that are public or were reported in a previous audit, are never eligible for a reward.

#### Payouts

* Do not try to cajole a protocol customer into paying you. Always use the provided Sherlock resolution mechanisms.&#x20;
* Sherlock pays rewards and deposit refunds in USDC on Polygon by default. Some programs pay rewards on a different network or in a different token; the program page will say.
* You don't need to complete identity verification (KYC) to submit a report. Some protocols require it before paying a reward; the program page will say.

### Protocol Customers

#### Ethical Standards

* Do not communicate with the whitehat outside of the official channel provided by Sherlock.
* Do not pay whitehats who submit bugs on Sherlock outside of Sherlock’s designated channel or without Sherlock’s consent.
* Do not claim a report is a known issue or duplicate without dated evidence that you knew of it before the whitehat's submission timestamp. That evidence can be public (an audit report, a merged fix, a fix PR in your repository) or private (a private fix PR, an earlier report submitted elsewhere, or a dated internal ticket or screenshot shared with Sherlock).
* Always default to the assumption that the whitehat has good intentions.
* By listing your bug bounty program on Sherlock, you are agreeing to abide by the outcome of the Sherlock dispute resolution process.

<br>
