---
original: https://github.com/sherlock-audit/2024-02-perpetual-judging/issues/118
---

# The attacker will steal funds from LPs

### Summary

Calculating the price based on USD value and not USDT/USDC will cause loss of funds for LPs as the attacker will withdraw more funds during the USDC/USDT de-peg.

### Root Cause
The choice to denominate all the tokens value in USD is a mistake as USDT/USDC (collateral tokens) are susceptible to de-pegs and allow to withdraw more value than the attacker should be able to.

### Internal pre-conditions

-

### External pre-conditions
The USDC/USDT price to be less than $1

### Attack Path:
1. The attacker calls [`withdraw`] during USDC/USDT 30% de-peg, but their collateral is still valued as there's no de-peg (100% instead of 70%).

### Impact
The other LPs suffer an approximate loss of 30%. The attacker gains this 30%.

### PoC

-

### Mitigation
Use the \<quote-token>/USD oracle to convert the \<base-token>/USD price to a \<base-token>/\<quote-token> oracle