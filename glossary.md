# Glossary

## Sherlock Terminology

### Claim

- A claim occurs when a protocol covered by Sherlock believes it has been hacked and believes Sherlock has a responsibility to repay the hack. See the [claims section](https://docs.sherlock.xyz/claims/claims-process) for details.

### Coverage

- If Sherlock takes on a protocol as a customer, the "coverage" is the amount of tokens (USDC) that Sherlock will reimburse when an exploit (that falls under the coverage agreement) occurs.

### Exploit

- For Sherlock's purposes, an exploit is the act of maliciously removing tokens (usually tokens deposited by others) from a protocol in an unintended way. Sherlock covers most (but not all) exploits that a protocol could experience. For a detailed breakdown of which exploits are generally covered, take a look at our current coverage agreements [here](https://github.com/sherlock-protocol/sherlock-reports/tree/main/coverage-agreements).

### Premium

- The amount of USDC a protocol pays Sherlock over a specified time interval. In return, Sherlock reimburses covered exploits experienced by the protocol over that same time interval.

### SHER

- Sherlock's governance token. See the [SHER section](https://docs.sherlock.xyz/tokens/sher) for more info.

### Staking

- The act of depositing USDC into a Sherlock staking pool for a fixed period (6 months, 12 months, etc.). Once USDC has been deposited, USDC and SHER tokens accrue to the depositor in the form of APY. A portion of the staked tokens (up to 50% for an individual exploit) in the staking pool is at risk of being liquidated due to an exploit at one of the protocols covered by Sherlock.

### Unstaking

- The act of removing staked USDC from the Sherlock staking pool. This action can only be taken once the staking period (6 months, 12 months, etc.) for that USDC has ended.

### Watsons

- "You know my methods, Watson. There was not one of them which I did not apply to the inquiry." - _The Memoirs of Sherlock Holmes_ (1893)
- Watsons are the individuals without which Sherlock would be nothing. These are the security experts who do the deep fundamental analyses (audits) that allow Sherlock to confidently provide coverage for a given protocol's smart contracts.

### Yield Strategy

- If Sherlock didn't have yield strategies, then a staker's USDC stake would sit idly in Sherlock's contracts until the staking period ends. Instead, Sherlock puts that USDC to work in other protocols in an effort to earn more APY for stakers. View the current yield strategies on our [dashboard](https://app.sherlock.xyz/overview "Sherlock dashboard")
