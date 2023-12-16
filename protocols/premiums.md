# Coverage Premiums

Once an agreement has been reached on the cover amount (e.g. $500k) and the price of coverage, Sherlock can calculate the per-second USDC premium that the protocol will pay at any given time.&#x20;

### Maintaining an Active Balance

A protocol will add USDC to its active balance in Sherlock's Protocol Manager contract. Protocols can manage their active balance [here](https://app.sherlock.xyz/protocols/balance). In order to stay current on payment, the protocol must simply keep the balance above a minimum USDC amount (currently 500 USDC) and a minimum amount of seconds of coverage left (set to 12 hours). If a protocol's active balance drops below either of these thresholds, an arbitrager can remove the protocol from coverage for a fee. For the 12-hour minimum, the arbitrager fee increases linearly over time to ensure the arbitrager doesn't receive an egregiously large fee. Once a protocol's coverage ends, Sherlock is no longer responsible for repaying any payouts that occur. But when a protocol's coverage first ends, it will have a 7-day window to submit claims for payouts that may have occurred when the coverage was still active.

If a protocol decides it wants to withdraw USDC from its active balance, it is perfectly free to do so. However, there is a minimum level of USDC that cannot be withdrawn (7 days worth). This is to give Sherlock time to react if a protocol decides to cancel its coverage. A protocol is free to cancel coverage at any time, it will just not be able to withdraw its last 7 days worth of payment. A protocol can also decide to run down the last 7 days of coverage instead of canceling, at which point an arbitrager will eventually remove the protocol when the balance is very low (i.e. 500 USDC or a few hours from being exhausted).

### Fluctuating TVL

If Sherlock's staking pool TVL sinks below a threshold (defined in the coverage agreement) of the coverage policy amount (i.e. $500k) for any reason, then Sherlock will only charge based on the amount of coverage being offered. This prevents a protocol team from being overcharged in a scenario where Sherlock can no longer pay out the full coverage amount.&#x20;
