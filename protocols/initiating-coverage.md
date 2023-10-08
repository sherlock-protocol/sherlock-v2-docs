# Initiating Coverage

Any protocol with funds locked in its smart contracts for any period of time can lose those funds due to an exploit. Therefore, any such protocol can benefit from exploit protection. Once an agreement is reached about what types of coverage a protocol is looking for (the coverage agreement), the security team can begin a security assessment. A security assessment will likely take a few days to a few weeks and it will assess not only the risk of exploits in smart contracts (and smart contract bugs), but also areas like the development practices of the team, the risk management processes built into the protocol and the safety of protocols that said protocol interacts with.

From this assessment, Sherlock's security and risk teams will agree on a price they would be comfortable charging the protocol. The security and risk teams will mostly come up with the “floor” price or the lowest price at which they would feel comfortable insuring a certain protocol.

Sherlock and the protocol will also agree on the dollar value to be insured. If the protocol’s TVL is $500M, maybe they will want $500M to be covered or maybe they will only have a special $100M pool that they want covered. For now, size of Sherlock's staking pools needs to be at least 3x bigger than the size of any pools to be covered for a protocol.

For example, a protocol wants $100M covered. Sherlock would need to have at least $300M in the staking pools, otherwise there would need to be a different agreement put in place. Because of the possibility of outflows from Sherlock's staking pools, Sherlock may implement a buffer amount (10% for example) to account for fluctuations in the size of Sherlock's staking pool.
