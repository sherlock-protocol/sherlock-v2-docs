---
original: https://github.com/sherlock-audit/2024-02-perpetual-judging/issues/118
---

# The attacker will steal funds from SpotHedgeBaseMaker LPs

### Summary

Calculating the price based on USD value and not USDT/USDC will cause loss of funds for SpotHedgeBaseMaker LPs as the attacker will withdraw more funds during the USDC/USDT de-peg.


### Root Cause

The choice to denominate all the tokens value in USD is a mistake as USDT/USDC (collateral tokens) are susceptible to de-pegs and allow to withdraw more value than the attacker should be able to.


### Internal pre-conditions

1. The vault LP account (PnL for all of the SpotHedgeBaseMaker's LPs) has a non-zero collateral token balance
2. The SpotHedgeBaseMaker has a non-zero base token balance
3. The attacker holds LP shares worth less than or equal to the SpotHedgeBaseMaker's base tokens holding's value

### External pre-conditions

1. The USDC/USDT price to be less than $1


### Attack Path:

1. The attacker calls [`withdraw`] during USDC/USDT 30% de-peg for an amount less than or equal to the base token balance, but the collateral tokens are still valued as if there's no de-peg (100% instead of 70%).


### Impact

The other LPs suffer an approximate loss of 30% when the collateral tokens need to be swapped to base tokens. The attacker gains this 30%, having not had to do the swap.


### PoC

-


### Mitigation

Use the \<quote-token>/USD oracle to convert the \<base-token>/USD price to a \<base-token>/\<quote-token> oracle