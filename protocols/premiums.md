# Premiums

Once an agreement has been reached on the cover amount (e.g. $100M) and the price of coverage (e.g. 2%), then Sherlock can calculate the per-second USDC premium that the protocol will pay.

### Maintaining an Active Balance

A protocol will add USDC to its active balance in Sherlock's Protocol Manager contract. In order to stay current on payment, the protocol must simply keep the balance above a minimum $ amount ($300) and a minimum amount of seconds of coverage left (i.e. 24 hours). If a protocol's active balance drops below either of these thresholds, an arbitrager can remove the protocol from coverage for a fee. For the 24 hour minimum, the arbitrager fee increases linearly over time to ensure the arbitrager doesn't receive an egregiously large fee. Beyond the timestamp when a protocol's coverage ends, the protocol can no longer submit claims for exploits that may occur. When a protocol's coverage ends, it will stay have a 7-day window to submit claims for exploits that may have occurred when the coverage was still active.&#x20;

If a protocol decides it wants to withdraw USDC from its active balance, it is perfectly free to do so. However, there is a minimum level of USDC that cannot be withdraw (i.e. 7 days worth). This is to give Sherlock time to react if a protocol decides to cancel its coverage. A protocol is free to cancel coverage at any time, it will just not be able to withdraw its last 7 days worth of payment. A protocol can also decide to run down the last 7 days of coverage instead of cancelling, at which point an arbitrager will eventually remove the protocol when the balance is very low (i.e. $300 or a few hours from being exhausted).&#x20;

### Fluctuating TVL

A protocol may agree to a $100M coverage policy, but find that its TVL is below $100M for a period of time. Instead of charging more than Sherlock is actually covering, the premium gets updated weekly based on the TVL being covered that week. Sherlock has an off-chain script that manages this process.&#x20;

&#x20;
