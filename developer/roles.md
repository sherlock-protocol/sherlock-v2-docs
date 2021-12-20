# Protocol Roles

### Contract roles

Manager: Current address for the overarching manager contract used by Sherlock (Manager.sol)
ISherlock: Current address for the contract that manages governance and staking used by Sherlock (Sherlock.sol)
IStrategyManager: Current address for the yield strategy contract used by Sherlock (AaveV2Strategy.sol)
ISherDistributionManager: Current address for the distribution manager contract used by Sherlock (SherDistributionManager.sol)
ISherlockProtocolManager: Current address for the protocol manager contract used by Sherlock (SherlockProtocolManager.sol)
ISherlockClaimManager: Current address for the claim manager contract used by Sherlock (SherlockClaimManager.sol)

### onlyOwner and owner
Manager.sol and Sherlock.sol implement OpenZeppelin's Ownable library. In both cases, the owner address will be a multi-sig controlled by the Sherlock core team. 

### onlySherlockCore
This role means that only the address associated with the active Sherlock.sol implementation can call the function.

## Sherlock.sol

### nonStakersAddress
This role will start out as a wallet controlled by the Sherlock core team. This wallet is where all compensation owed to Watsons or other parties (reinsurance, etc.) will be collected and distributed by the Sherlock core team. 

Soon, this role will be changed to a smart contract (instead of a wallet) which will manage this process on-chain. 

### NFT Owner roles
Functions like _verifyUnlockableByOwner() and ownerRestake() actually refer to the owner of the NFT (representing a stake position) and NOT the owner of the Sherlock.sol smart contract instance. 

## SherlockClaimManager.sol

### onlyUMA and UMA
This role is the address of UMA's active Skinny Optimistic Oracle implementation. It also requires the UMA contract to pass in Sherlock's identifier to ensure that the UMA contract is referring to a Sherlock claim. Sherlock employs certain callbacks that should only be called by UMA's active Skinny Optimistic Oracle address. 

### onlyUMAHO and umaHaltOperator 
This role is a multi-sig wallet controlled by the UMA core team. The idea is that if the UMA Optimistic Oracle malfunctions for any reason, there is a fallback where the UMA core team can halt a claims process and allow a claim to be re-submitted. 

It is still TBD as to whether this functionality will be implemented or not, as it comes with tradeoffs around centralization. Once this functionality is removed, it cannot be added back. This allows users to know that re-centralization is not possible. 

### onlySPCC and sherlockProtocolClaimsCommittee
This role is a multi-sig wallet controlled by top security experts in the space and elected by the Sherlock core team. 

This multi-sig is the initial step of a claims process. The SPCC will provide and quick and educated decision on a claims payout. If a protocol does not like the decision and thinks there was bias or other foul play, the protocol can escalate the claims decision to UMA's Optimistic Oracle. 

## SherlockProtocolManager.sol

### protocolAgent, _verifyProtocolExists() and protocolExists modifier
The role of protocol agent is an address that is associated with each protocol customer and can take actions on behalf of that protocol. For example, a claim for a protocol can only be initiated by the protocol agent and excess funds can only be withdrawn (on behalf of a protocol) by the protocol agent. 

Having an active protocol agent is also a way that Sherlock checks to see if a protocol exists in the Sherlock system or not. 


