# Audit Pricing and Timeline

Each audit consists of a fixed pay element to properly compensate and incentivize dedicated senior auditors, as well as a prize pool for all contestants to compete to win. In order to properly align incentives with protocols, Sherlock offers up to $5M in smart contract exploit coverage behind every audit (not included in audit cost below), which can be activated at any point after the audit is completed, provided there haven’t been subsequent changes to the code base. As a result, Sherlock has developed the following broad underwriting guidelines for how much time is needed to complete an audit of codebases of various sizes in order to offer smart contract coverage on the protocol in the future.

| **Solidity Lines (nSLOC)** | 500      | \~1000   | \~2000    | \~3000    | \~4000    | \~5000    | \~6000    | \~7000    | \~8000    |
| -------------------------- | -------- | -------- | --------- | --------- | --------- | --------- | --------- | --------- | --------- |
| **Pricing**                | \~$19k   | \~$39k   | \~$77k    | \~$118k   | \~$160k   | \~$203k   | \~$247k   | \~$291k   | \~$337k   |
| **Audit Timeline**         | \~3 days | \~6 days | \~12 days | \~19 days | \~25 days | \~32 days | \~39 days | \~46 days | \~53 days |

> Note: Sherlock utilizes the tool [Solidity Metrics](https://github.com/ConsenSys/solidity-metrics) to calculate nSLOC.\
> \
> \*Given the exponential complexity of very large codebases for any security expert, Sherlock will have final discretion whether to write smart contract coverage behind its audit for protocols with >6000 nSLOC

Sometimes a protocol will need extra audit time instead of a 0.5 day fix review after their initial audit. This is very normal. In this case, Sherlock believes the protocol should do another (shorter) contest. This "shorter" contest will not need to follow the nSLOC guidelines above, because most auditors will already be familiar with it and have audited it a couple weeks prior. The cost/length of the follow-up audits will be dependent on the scoping of the Lead Senior Watson of follow-up audit (Sherlock has a 3-day, $19k minimum size of contests currently).&#x20;
