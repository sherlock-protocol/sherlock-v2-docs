# Sherlock V2 Technical overview

> Repo: https://github.com/sherlock-protocol/sherlock-v2-core

## Architecture

The [core contract](https://github.com/sherlock-protocol/sherlock-v2-core/blob/main/contracts/Sherlock.sol) (Sherlock.sol) is the main point of interaction for stakers. The contract has an upgradeable reference to 5 addresses.

1. Yield strategy (AaveV2Strategy.sol)
2. SHER rewards (SherDistributionManager.sol)
3. Protocol manager (SherlockProtocolManager.sol)
4. Claims/payout process (SherlockClaimManager.sol)
5. Non-Staker address (multisig wallet)

![Architecture overview](https://i.imgur.com/tJ7hH7z.jpg)

Core holds USDC and the exact amount of SHER that will be distributed to stakers upon exiting their position.

Yield strategy holds most of the USDC as the owner of the core contract can move funds into Aave V2 and earn yield.

Protocol manager holds all the balances deposited by protocols and exposes the exact amount of debt to core, which is claimable each block.

The claims/payout process contract is not supposed to hold funds.

The non-staker address is able to claim funds from protocol manager based on the configuration of each covered protocol.

> Every contract is ownable

## Objects

Conceptually there a couple objects with a lifecycle

- Stake position (Core)
- Claim (Claim manager)
- Protocol (Protocol manager)
- SHER Rewards Curve (SHER distribution manager)

Each object and their lifecycle can be viewed in the specific docs
