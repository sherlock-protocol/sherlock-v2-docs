---
original: https://github.com/sherlock-audit/2024-04-titles-judging/issues/269
---

# Protocol will not refund excess fees to users

### Description
The incorrect `msg.value` in Edition.sol will cause a loss of excess fees for users as the protocol will send the entire `msg.value` into `FeeManager` contract instead of `mintFee`.

### Root Cause
In [`Edition.sol::mint::L236`](https://github.com/sherlock-audit/2024-04-titles/blob/d7f60952df22da00b772db5d3a8272a988546089/wallflower-contract-v2/src/editions/Edition.sol#L236) the entire `msg.value` is sent to FeeManager, but is not returned back in [`FeeManager::collectMintFee`](https://github.com/sherlock-audit/2024-04-titles/blob/d7f60952df22da00b772db5d3a8272a988546089/wallflower-contract-v2/src/fees/FeeManager.sol#L183). Hence, if excess ETH is sent, it's not refunded to the user on [`Edition::mint::L241`](https://github.com/sherlock-audit/2024-04-titles/blob/d7f60952df22da00b772db5d3a8272a988546089/wallflower-contract-v2/src/editions/Edition.sol#L241).

### Internal pre-conditions

1. The work publisher needs to call [`Edition::setFeeStrategy`](https://github.com/sherlock-audit/2024-04-titles/blob/d7f60952df22da00b772db5d3a8272a988546089/wallflower-contract-v2/src/editions/Edition.sol#L368) to set `mintFee` to go from `X` to `<X`

### External pre-conditions

__-__

### Attack Path
1. The work publisher calls and decreases the `mintFee` from 0.05 ETH to 0.03 ETH.
2. The user calls [`Edition::mint`](https://github.com/sherlock-audit/2024-04-titles/blob/d7f60952df22da00b772db5d3a8272a988546089/wallflower-contract-v2/src/editions/Edition.sol#L228) and uses an outdated version as he calls with 0.05 ETH as `msg.value` to pay the 0.03 ETH `mintFee`

### Impact
The user suffers an approximate loss of 0.02 ETH. In reality, the loss is equal to any value by which this parameter was reduced

### PoC

### Mitigation
Call `mintFee` at the very start of `mint` function and send the received value to `FeeManager`:
```diff
    function mint(
        address to_,
        uint256 tokenId_,
        uint256 amount_,
        address referrer_,
        bytes calldata data_
    ) external payable override {
+       uint256 mintFee = mintFee(tokenId_, amount_);
        // wake-disable-next-line reentrancy
-       FEE_MANAGER.collectMintFee{value: msg.value}(
+       FEE_MANAGER.collectMintFee{value: mintFee}(
            this, tokenId_, amount_, msg.sender, referrer_, works[tokenId_].strategy
        );

        _issue(to_, tokenId_, amount_, data_);
        _refundExcess();
    }
    ```