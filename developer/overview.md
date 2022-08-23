# Overview

> Repo: https://github.com/sherlock-protocol/sherlock-v2-core

## Architecture

The [core contract](https://github.com/sherlock-protocol/sherlock-v2-core/blob/main/contracts/Sherlock.sol) (Sherlock.sol) is the main point of interaction for stakers. The contract has an upgradeable reference to 5 addresses.

1. Yield strategy (MasterStrategy.sol)
2. SHER rewards (SherDistributionManager.sol)
3. Protocol manager (SherlockProtocolManager.sol)
4. Claims/payout process (SherlockClaimManager.sol)
5. Non-Staker address (multisig wallet)

![Architecture overview](https://i.imgur.com/faompEY.png)

Core holds USDC and the exact amount of SHER that will be distributed to stakers upon exiting their position.

The yield strategy holds most of the USDC as the owner of the core contract can move funds into to the Master Strategy contract which will distribute the USDC between different protocols based on a preconfigured distribution.

Protocol manager holds all the balances deposited by protocols and exposes the exact amount of debt to core, which is claimable each block.

The claims/payout process contract is not supposed to hold funds.

The non-staker address is able to claim funds from protocol manager based on the configuration of each covered protocol.

## Lifecycles

Conceptually there a couple objects with a lifecycle

* Stake position (Core)
* Claim (Claim manager)
* Protocol (Protocol manager)
* SHER Rewards Curve (SHER distribution manager)

Each object and their lifecycle can be viewed in the specific docs

## Roles

Some of the contracts used in Sherlock V2 implement access control for certain functions.

For Ownable, the openZeppelin's Ownable library is being used. The owner address will belong to Sherlock governance.

### Sherlock.sol

**Ownable**

1. `enableStakingPeriod()`
2. `disableStakingPeriod()`
3. `updateSherDistributionManager()`
4. `removeSherDistributionManager()`
5. `updateNonStakersAddress()`
6. `updateSherlockProtocolManager()`
7. `updateSherlockClaimManager()`
8. `updateYieldStrategy()`
9. `pause()`
10. `unpause()`
11. `yieldStrategyDeposit()`
12. `yieldStrategyWithdraw()`
13. `yieldStrategyWithdrawAll()`

Functions 1 to 8 are functions calls that have a big effect on the way the protocol executes.

Functions 9 and 10 are used in emergency situations when the protocol needs to be paused for investigation.

Function 11, 12 and 13 are used to move the staker pool in and out of the active strategy.

### MasterStrategy.sol

**Ownable**

1. `withdrawAllByAdmin()`
2. `withdrawByAdmin()`

These functions are used to get USDC out of the underlying strategies.

**onlySherlockCore**

This role means that only the address associated with the active Sherlock.sol implementation can call the function.

1. `deposit()`
2. `withdrawAll()`
3. `withdraw()`

These functions are used to get liquidity in and out of the underlying strategies.

### SherDistributionManager.sol

**Ownable**

1. `sweep()`

This function is used to get the remaining ERC20s and ETH out of the contract. This can only be called if it isn't the current active sher distribution manager.

### SherlockProtocolManager.sol

**Ownable**

1. `setMinActiveBalance()`
2. `protocolAdd()`
3. `protocolUpdate()`
4. `protocolRemove()`
5. `setProtocolPremium()`
6. `setProtocolPremiums()`
7. `sweep()`

This function is used to get the remaining ERC20s and ETH out of the contract. This can only be called if it isn't the current active sher distribution manager.

**Protocol Agent**

1. `withdrawActiveBalance()`

These function can only be called by the protocol agent, there are as many protocol agents as there are protocols.

**Non Stakers**

1. `nonStakersClaim()`

This function can only be called by the `nonStakersAddress`, which is defined in `Sherlock.sol`

### SherlockClaimManager.sol

**Ownable**

1. `renounceUmaHaltOperator()`
2. `addCallback()`
3. `removeCallback()`

**Protocol Agent**

1. `startClaim()`
2. `escalate()`
3. `payoutClaim()`
4. `cleanUp()`

These function can only be called by the protocol agent, there are as many protocol agents as there are protocols. This agent retrieved from `SherlockProtocolManager.sol`

NOTE: Function 2 and 3 use the stored protocol agent of `startClaim()`

**UMA**

> Read more about our UMA integration here https://docs.sherlock.xyz/claims/claims-process

1. `priceProposed()`
2. `priceDisputed()`
3. `priceSettled()`

These functions can only be called by `UMA`, this is a hardcoded address in `SherlockClaimManager.sol`

**UMAHO**

1. `executeHalt()`

These functions can only be called by `UMAHO` (UMA Halt Operator), this is an address passed on in the constructor of `SherlockClaimManager.sol`

**SPCC**

1. `spccApprove()`
2. `spccRefuse()`

These functions can only be called by `SPCC` (Sherlock Protocol Claims Committee), this is an address passed on in the constructor of `SherlockClaimManager.sol`
