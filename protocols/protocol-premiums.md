# Protocol Premiums

Once an agreement has been reached on the cover amount (e.g. $100M) and the price of coverage (e.g. 2%), then Sherlock can calculate the per-block premium that the protocol will pay.

Because it’s extremely gas-inefficient to send a payment every block, the protocol will initially send at least two weeks worth of payment up front. The payment for the first week will be “drawn down” in Sherlock's internal accounting block-by-block and the payment for the second week will be a buffer, just in case there is some problem with payment once the first week has been drawn down.

In this way, a protocol can manage its payment by sending one week's payment at a time (or a months’ worth of prepay if they want to) after the initial deposit. If a protocol isn’t able to pay for whatever reason, the coverage stops at the block where the payment stream ended.
