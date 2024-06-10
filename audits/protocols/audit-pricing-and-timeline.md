# Audit Timeline

Each Sherlock audit consists of a fixed pay element to adequately incentivize at least 1 dedicated Senior Watson to lead the audit as well as a prize pool element that often draws 200-400 independent auditors.&#x20;

In order to properly align incentives with protocols, Sherlock offers smart contract coverage behind qualifying audits (not included in the audit cost), which can be activated at any point after the audit is completed, provided the fix review has been completed and there haven’t been subsequent changes to the code base.&#x20;

Sherlock has developed the following broad underwriting guidelines for how much time is needed to complete an audit of codebases of various sizes in order to offer smart contract coverage on the protocol in the future:

<table data-header-hidden><thead><tr><th width="229">Solidity Lines (nSLOC)</th><th width="145">Audit Timeline</th></tr></thead><tbody><tr><td>~500</td><td>~3 days</td></tr><tr><td>~1000</td><td>~6 days</td></tr><tr><td>~2000</td><td>~12 days</td></tr><tr><td>~3000</td><td>~18 days</td></tr><tr><td>~4000</td><td>~25 days</td></tr><tr><td>~5000</td><td>~32 days</td></tr><tr><td>~6000</td><td>~38 days</td></tr></tbody></table>

> Note: Sherlock utilizes the tool [Solidity Metrics](https://github.com/ConsenSys/solidity-metrics) to calculate nSLOC.\
> \
> \*Given the exponential complexity of very large codebases for any security expert, Sherlock will have final discretion whether to write smart contract coverage behind its audit for protocols with >6000 nSLOC

Sometimes a protocol will need extra audit time instead of a 1-day fix review after their initial audit. This is very normal. In this case, Sherlock recommends another (shorter) contest in order to be eligible for smart contract coverage. This "shorter" contest will not need to follow the nSLOC guidelines above, because most auditors will already be familiar with it and will have audited it very recently. The cost/length of the follow-up audits will depend on the scoping/judgment of the Lead Senior Watson.
