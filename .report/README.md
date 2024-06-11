# Title
Structure: {actor} will {impact} {affected party}
Example:
- Malicious fee managers will steal funds from stakers
- Attacker will lower the APY for stakers
- Protocol will distribute insufficient fees to token holders

### Summary
Structure: {root cause} will cause [a/an] {impact} for {affected party} as {actor} will {attack/vulernability path}
Example:
- The missing check in stake.sol will cause a complete loss of funds for stakers as an attacker will frontrun their transactions
- An incorrect calculation in lp.sol will cause a DoS for admins as the protocol will revert on every update

### Root Cause

__In case it’s a mistake in the code:__
- In {link to code} the {root cause}

Example:
- In stake.sol:551 there is a missing check on transfer function
- In lp.sol:12 the fee calculation does division before multiplication which will revert the transaction on lp.sol:18

__In case it’s a conceptual mistake:__
- The choice to {design choice} is a mistake as {root cause}

Example:
- The choice to use Uniswap as an oracle is a mistake as the price can be manipulated
- The choice to depend on Protocol X for admin calls is a mistake as it will cause any call to revert

### Internal pre-conditions

A numbered list of conditions to allow the attack path or vulnerability path to happen:
1. [{Role} needs to {action} to set] {variable} to be [at least / at most / exactly] {value}
2. [{Role} needs to {action} to set] {variable} to go from {value} to {value} [within {time}]

Example
- Admin needs to call `setFee()` to set `fee` to be exactly `1 ETH`
- The number ETH in the `stake.sol` contract to be at least `500 ETH`

### External pre-conditions

> Similar to internal but it describes changes in the external protocols 

- The ETH oracle needs to go from 4000 to 5000 within 2 minutes
- The gas price needs to be exactly 100 wei

### Attack Path:

A numbered list of steps, talking through the attack path:
1. {Role} calls {function}.....

### Impact
In case it's an __attack path:__

The {affected party} suffers an approximate loss of {value}. [The attacker gains {gain} or loses {loss}.]

Example:
- The stakers suffer a 50% loss during staking. The attacker gains this 50% from stakers.
- The protocol suffers a 0.0006 ETH minting fee. The attacker loses their portion of the fee and doesn't gain anything (griefing).

In case it's a __vulnerability path:__

The {affected party} [(suffers an  approximate loss of {value} OR cannot {execute action})].

Example:
- Based on the described above scenario, the users suffer an approximate loss of 0.01% due to precision loss.
- Based on the described above scenario, the user cannot mint tokens.

### PoC

### Mitigation