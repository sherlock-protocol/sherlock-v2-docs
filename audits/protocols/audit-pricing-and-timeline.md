# Audit Pricing and Timeline

Each audit consists of a fixed pay element to properly compensate and incentivize dedicated senior auditors, as well as a prize pool for all contestants to compete to win. In order to properly align incentives with protocols, Sherlock underwrites each audit with up to $10M in smart contract coverage, which can be activated at any point after the audit is completed, provided there haven’t been subsequent changes to the code base. As a result, Sherlock has developed the following broad underwriting guidelines for how much time is needed to complete an audit of codebases of various sizes in order to comfortably write coverage behind the audit in the future.

| **Solidity Lines (nSLOC)** | <500     | \~1000   | \~1500 - 3000 | \~3500 - 5000 | >5000     |
| -------------------------- | -------- | -------- | ------------- | ------------- | --------- |
| **Pricing**                | \~$15k   | \~$38k   | \~75k         | \~$113k       | \~$150k+  |
| **Audit Timeline**         | \~3 days | \~7 days | \~14 days     | \~21 days     | \~28 days |

> Note: Sherlock utilizes the tool [Solidity Metrics](https://github.com/ConsenSys/solidity-metrics) to calculate nSLOC.

Sometimes a protocol will need extra audit time instead of a 0.5 day fix review after their initial audit. This is very normal. In this case, Sherlock believes the protocol should do another (shorter) contest. This "shorter" contest will not need to follow the nSLOC guidelines above, because most auditors will already be familiar with it and have audited it a couple weeks prior. We are thinking that the follow-up audits will follow the chart above, but with their nSLOC divided by 2, to decide the length/cost of their follow-up audit. &#x20;
