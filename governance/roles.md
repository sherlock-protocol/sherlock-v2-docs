# Protocol Roles

### Governance Functionality
While the protocol is quite governance-minimized, there are still some aspects that will be controlled by a governing party. At launch, a multi sig controlled by the Sherlock core team will be in control of upgrades, pausing and functionality related to adding and removing covered protocols. Over time, this functionality will be turned over to a DAO that will be in full control of the parts of the Sherlock protocol which can be changed. 

### Sherlock Protocol Claims Committee
This committee is the first responder when it comes to claims submitted by protocols. The SPCC is made up of core Sherlock team members as well as well-known security experts in the space including John Mardlin and Rajeev Gopalakrishna. This committee controls a multisig that accepts or denies a protocol's claim submission. If a protocol does not agree with the committee's decision, it has the ability to escalate to the UMA Optimistic Oracle, as explained in the [Claims](https://docs.sherlock.xyz/claims/claims-process) section. 

### UMA Halt Operator
This is another multi sig that will be controlled by the core UMA team. Basically, the UMA Optimistic Oracle is completely trustless so for the first few months Sherlock has requested to have an "emergency halt" mechanism. This mechanism will be controlled by the UMA core team and allow UMA to deny/halt a claim that is moving through the UMA Optimstic Oracle in case something breaks. The protocol who submitted the claim will then be able resubmit the claim once a fix is made. This mechanism will be removed after a few months and there will be no functionality to add it back, fulfilling the promise of a truly trustless claims process. 

### Protocol Agent
A protocol agent is simply a wallet or multi sig controlled by a covered protocol. This agent will have the ability to do protocol-specific actions like submitting claims and withdrawing unused funds (in the case of overpayment). 

### NFT Owners
When a staker deposits funds into Sherlock, the staker receives an NFT in return. If the staker tries to unstake but no longer holds the NFT, the unstake transaction will fail. Only the owner of the NFT at any given time can do important actions that are specific to the NFT position. The only exception is restaking done by arbitragers, discussed in the [Unstaking](https://docs.sherlock.xyz/stakers/lockup-period#unstaking) section. 

