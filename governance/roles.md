# Protocol Roles

### Governance Functionality
While the protocol is quite governance-minimized, there are still some aspects that will be controlled by a governing party. At launch, a multi sig controlled by the Sherlock core team will be in control of upgrades, pausing and functionality related to adding and removing covered protocols. Over time, this functionality will be turned over to a DAO that will be in full control of the parts of the Sherlock protocol which can be changed. 

### Sherlock Protocol Claims Committee
As described in the [Claims](https://docs.sherlock.xyz/claims/claims-process) section, the Sherlock Protocol Claims Committee (or SPCC) is the first of two arbitration mechanisms that decide whether a claim should be paid out or not. 

The SPCC is optimized for speed, at the expense of some potential for bias. If some amount of bias is believed to have occured, a protocol can escalate their claim above the authority of the SPCC, and put it in the hands of the UMA Optimistic Oracle. The UMA OO is a slower process but the claim decision is made by tens of thousands of UMA tokenholders who, as a whole, are probably not biased towards Sherlock or the protocol submitting the claim. 

The SPCC is made up of core Sherlock team members as well as well-known security experts in the space. This committee controls a multisig that accepts or denies a protocol's claim submission. Again, if the committee votes in a way that the protocol disagrees with, the protocol can escalate to the UMA Optimistic Oracle. 

The address of the SPCC is: 0x4Fcf6AA323a92EB92a58025E821f393da6C41bD6

The current members of the SPCC are:

| Name                    | Address                                                                                                                |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [Jack Sanford](https://twitter.com/jack__sanford) | 0xfcb7493E4a059eF1CCBb53e71Cb94cc5d3d380bf |
| [Evert Kors](https://twitter.com/Evert0x) | 0x3ea15C2EaF93bA32172EB8A789B937255624c24c |
| [John Mardlin](https://twitter.com/maurelian_) | 0xF0001193a7919B14417c038604846D7b3F8F4BC3 |
| [Rajeev Gopalakrishna](https://twitter.com/0xRajeev) | 0x7e026a0C061382B0F5935a90BC7324ab0a5A3aCc |
| [Emiliano Bonassi](https://twitter.com/emilianobonassi) | eth:0x36388492077FBE730e82b408E6bec3318C54d6c3 |
| [Mikko Ohtamaa](https://twitter.com/moo9000) | 0x7FfAB8b2f131AF752319A1641B52ac0a9bbB41B7 |
| [Mick de Graaf](https://twitter.com/MickdeG010) | 0x0C42567e180CdEdd5B4C690678B6662D74193457 |


### UMA Halt Operator
This is another multi sig that will be controlled by the core UMA team. Basically, the UMA Optimistic Oracle is completely trustless so for the first few months Sherlock has requested to have an "emergency halt" mechanism. This mechanism will be controlled by the UMA core team and allow UMA to deny/halt a claim that is moving through the UMA Optimstic Oracle in case something breaks. The protocol who submitted the claim will then be able resubmit the claim once a fix is made. This mechanism will be removed after a few months and there will be no functionality to add it back, fulfilling the promise of a truly trustless claims process. 

### Protocol Agent
A protocol agent is simply a wallet or multi sig controlled by a covered protocol. This agent will have the ability to do protocol-specific actions like submitting claims and withdrawing unused funds (in the case of overpayment). 

### NFT Owners
When a staker deposits funds into Sherlock, the staker receives an NFT in return. If the staker tries to unstake but no longer holds the NFT, the unstake transaction will fail. Only the owner of the NFT at any given time can do important actions that are specific to the NFT position. The only exception is restaking done by arbitragers, discussed in the [Unstaking](https://docs.sherlock.xyz/stakers/lockup-period#unstaking) section. 

