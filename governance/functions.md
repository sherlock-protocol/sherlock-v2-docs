# Owner role

Sherlock strives to be a decentralized but effective protocol. The owner of every contract is able to perform sensitive functions, this section describes how this role will be transferred to SHER token holders over time.

## Governance function list

Functions that are restricted to the owner in every contract.

### Sherlock.sol

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

### AaveV2Strategy.sol

14. `sweep()`

### SherDistributionManager.sol

15. `sweep()`

### SherlockProtocolManager.sol

16. `setMinActiveBalance()`
17. `protocolAdd()`
18. `protocolUpdate()`
19. `protocolRemove()`
20. `setProtocolPremium()`
21. `setProtocolPremiums()`
22. `sweep()`

### SherlockClaimManager.sol

23. `renounceUmaHaltOperator()`
24. `addCallback()`
25. `removeCallback()`

## Roadmap

The access to these functions will be moved to the right entity with the right timelock to make Sherlock decentralized and effective.

### Q1-Q2 2022

At launch we will use the default OpenZeppelin `TimelockController`, the timelock will be 0 for the first 2 weeks after deployment to allow quick mitigation by the team in case something goes wrong. After 2 weeks the timelock will be 48 hours until we move to the next stage.

> Only the timelock is able to change it's proposal and executor role, as the multisig is able to execute any call. It is able to change the roles

The multisig will be the only address than can propose function calls. Alongside the multisig two EOA's managed by the team are allowed to execute functions.

| Function                                          | Multisig | Timelock |
| ------------------------------------------------- | -------- | -------- |
| 1. `enableStakingPeriod()`                        | x        | 48 hours |
| 2. `disableStakingPeriod()`                       | x        | 48 hours |
| 3. `updateSherDistributionManager()`              | x        | 48 hours |
| 4. `removeSherDistributionManager()`              | x        | 48 hours |
| 5. `updateNonStakersAddress()`                    | x        | 48 hours |
| 6. `updateSherlockProtocolManager()`              | x        | 48 hours |
| 7. `updateSherlockClaimManager()`                 | x        | 48 hours |
| 8. `updateYieldStrategy()`                        | x        | 48 hours |
| 9. `pause()`                                      | x        | 48 hours |
| 10. `unpause()`                                   | x        | 48 hours |
| 12. `yieldStrategyWithdraw()`                     | x        | 48 hours |
| 13. `yieldStrategyWithdrawAll()`                  | x        | 48 hours |
| 14. `sweep()`                                     | x        | 48 hours |
| 15. `sweep()`                                     | x        | 48 hours |
| 16. `setMinActiveBalance()`                       | x        | 48 hours |
| 17. `protocolAdd()`                               | x        | 48 hours |
| 18. `protocolUpdate()`                            | x        | 48 hours |
| 19. `protocolRemove()`                            | x        | 48 hours |
| 20. `setProtocolPremium()`                        | x        | 48 hours |
| 21. `setProtocolPremiums()`                       | x        | 48 hours |
| 22. `sweep()`                                     | x        | 48 hours |
| 23. `renounceUmaHaltOperator()`                   | x        | 48 hours |
| 24. `addCallback()`                               | x        | 48 hours |
| 25. `removeCallback()`                            | x        | 48 hours |
| Update timelock proposers (grantRole, revokeRole) | x        | 48 hours |
| Update delays                                     | x        | 48 hours |

### Q3 2022

For the next stage we need custom timelocks and custom access to specific functions. Some calls are able to skip the timelock as stated with a `-`. Every other call will be at least subject to a 48 hour timelock.

The DAO is able to propose any arbitrary call while the Multisig and EOA are heavily restricted in the calls they can propose. At this stage every proposed function can be executed by anyone.

| Function                                          | DAO | Multisig | EOA | Timelock |
| ------------------------------------------------- | --- | -------- | --- | -------- |
| 1. `enableStakingPeriod()`                        | x   |          |     | 7 days   |
| 2. `disableStakingPeriod()`                       | x   |          |     | 7 days   |
| 3. `updateSherDistributionManager()`              | x   |          |     | 7 days   |
| 4. `removeSherDistributionManager()`              | x   |          |     | 7 days   |
| 5. `updateNonStakersAddress()`                    | x   |          |     | 7 days   |
| 6. `updateSherlockProtocolManager()`              | x   |          |     | 7 days   |
| 7. `updateSherlockClaimManager()`                 | x   |          |     | 7 days   |
| 8. `updateYieldStrategy()`                        | x   |          |     | 7 days   |
| 9. `pause()`                                      | x   | x        |     | -        |
| 10. `unpause()`                                   | x   | x        |     | -        |
| 11. `yieldStrategyDeposit()`                      | x   |          | x   | -        |
| 12. `yieldStrategyWithdraw()`                     | x   | x        |     | 48 hours |
| 13. `yieldStrategyWithdrawAll()`                  | x   | x        |     | 48 hours |
| 14. `sweep()`                                     | x   |          |     | -        |
| 15. `sweep()`                                     | x   |          |     | -        |
| 16. `setMinActiveBalance()`                       | x   |          |     | 7 days   |
| 17. `protocolAdd()`                               | x   | x        |     | 48 hours |
| 18. `protocolUpdate()`                            | x   | x        |     | 48 hours |
| 19. `protocolRemove()`                            | x   | x        |     | 48 hours |
| 20. `setProtocolPremium()`                        | x   | x        |     | 48 hours |
| 21. `setProtocolPremiums()`                       | x   | x        |     | 48 hours |
| 22. `sweep()`                                     | x   |          |     | -        |
| 23. `renounceUmaHaltOperator()`                   | x   |          |     | 7 days   |
| 24. `addCallback()`                               | x   |          |     | 7 days   |
| 25. `removeCallback()`                            | x   |          |     | 7 days   |
| Update timelock proposers (grantRole, revokeRole) | x   |          |     | 7 days   |
| Update delays                                     | x   |          |     | 0 - 7d\* |

\* Based on the delay of the function

### Q4 2022 and onward

Timelock and entities with accesss wil be decided by the DAO.
