---
original: https://github.com/sherlock-audit/2024-02-perpetual-judging/issues/123
---

# Title
Attacker will steal funds from LPs

### Summary

The choice to depend on Pyth oracles will cause a loss of funds for LPs as the attacker will use the Pyth oracles to manipulate the price during `deposit()` and `withdraw()`

### Root Cause

The choice to depend on Pyth oracles is a mistake as there is no guarantee that the current price is the freshest price

### Internal pre-conditions

-

### External pre-conditions

1. Two signed prices with a difference in price

### Attack Path

1. Attacker calls `deposit()` with the low price
2. Attacker calls `withdraw()` with the high price

### Impact

The LPs suffers an approximate loss of ...?

### Mitigation

Require that LP deposits and withdrawals be done by the trusted relayers or use a different oracle



