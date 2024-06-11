---
original: https://github.com/sherlock-audit/2024-04-titles-judging/issues/264
---

# An attacker will avoid paying fees to protocol and fee recepients.

### Summary
Incorrect values in [`Edition::mintBatch::L304`](https://github.com/sherlock-audit/2024-04-titles/blob/d7f60952df22da00b772db5d3a8272a988546089/wallflower-contract-v2/src/editions/Edition.sol#L304) will cause an almost complete loss of fees for the protocol and fee recepients as the attacker will pay only for one token.

### Root Cause
In [`Edition::mintBatch`](https://github.com/sherlock-audit/2024-04-titles/blob/d7f60952df22da00b772db5d3a8272a988546089/wallflower-contract-v2/src/editions/Edition.sol#L312C28-L312C37) the fees are calculated based on the `amount` of tokens to mint, when the minting itself is made on the number of recepients.

### Internal pre-conditions

__-__

### External pre-conditions

__-__

### Attack path

1. The attacker calls `mintBatch` with `amount_` set to 1 `receivers` set to 1000 addresses. At `L312` the code collects mint fee based on the `amount_` value. In this case fee for only 1 token will be taken. At `L315-L316` the code loops over each address in `receivers_` array and mints a new token for each. Hence, 1000 tokens are minted. The attacker paid fees for only one token, instead of 1000.

### Impact
The protocol and fee recepients suffer a 0.999 ETH loss. 

### Mitigation
Consider the following change to ensure that the minting is computed based on the total number of tokens minted to all receivers:
```diff
    function mintBatch(
        address[] calldata receivers_,
        uint256 tokenId_,
        uint256 amount_,
        bytes calldata data_
    ) external payable {
        // wake-disable-next-line reentrancy
        FEE_MANAGER.collectMintFee{value: msg.value}(
-            this, tokenId_, amount_, msg.sender, address(0), works[tokenId_].strategy
+            this, tokenId_, amount_ * receivers_.length, msg.sender, address(0), works[tokenId_].strategy
        );

        for (uint256 i = 0; i < receivers_.length; i++) {
            _issue(receivers_[i], tokenId_, amount_, data_);
        }

        _refundExcess();
    }
```