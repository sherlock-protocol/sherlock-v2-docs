# Interest Streams

As a user's stake remains in a staking pool over time, it will earn three different streams of interest.

## STREAM #1

A staker’s initial stake (i.e. USDC) will likely be swept into an “already insured” protocol like Aave or Compound -- where it will continuously earn market-rate interest.

**Why Aave or Compound?** The #1 priority for staking pool funds is principal preservation. It doesn’t make much sense to deposit staking pool funds into the very same ecosystem that needs coverage so badly. However, certain protocols have their own Sherlock-like funds (Aave being a notable one with the Safety Module). It seems justifiable to place Sherlock's staking pool funds into protocols that meet a certain standard of safety and have some type of coverage outside of Sherlock.

## STREAM #2

A staker will also earn interest from protocol payments. A protocol that is paying Sherlock for coverage will “stream” payment block-by-block for coverage. Sherlock is built to allow protocols to have lots of choice in their payment token. However, this will not be the case during Sherlock's guarded launch. Because protocols may eventually pay in a variety of tokens, a new token was introduced, called SherX, to represent a staker's proportional share in all the protocol payment tokens. If Sherlock covers 10 protocols and they are all paying in different tokens (often their governance token), it's very gas-intensive to pay stakers in 10 different tokens. So SherX is minted to represent a staker’s share of earned fees.

**Why mint SherX instead of paying stakers directly in protocol payment tokens?** It really comes down to gas. If Sherlock has 20 protocols on board and 20 different tokens being paid into the pool, it’s very costly on unstake to pay stakers in 20 different tokens. On top of that, the staker might have staked ETH and they just want more ETH. So they have to do 20 separate transactions after the first 20 transactions to get all the tokens into ETH. Whereas if SherX is minted to represent a proportional share of the 20 tokens, it’s more gas efficient and it will be easier for the staker to get from SherX to ETH or a specific token they want to hold. In order to make this possible, a Uniswap pool for SherX (SherX vs. ETH) will be created. In addition, anyone can redeem SherX tokens for the underlying collateral (the 20 different tokens, in this example) at any time using the redeem function. This will insure that SherX always trades fairly close to the value of its underlying collateral (because an arbitrager could buy discounted SherX tokens on Uniswap and redeem them for the full value of the underlying collateral).

**Will protocols be allowed to pay in tokens other than USDC after the guarded launch?** It seems unlikely at this point that Sherlock will allow protocols to pay in tokens other than USDC in the short to medium term. This means the SHERX mechanism is not very useful and it may be removed in future versions of the Sherlock protocol.

## STREAM #3

A staker may also receive Sherlock governance token (SHER) incentives. Especially as the staking pools are ramping up, the APY generated from protocol payments may not be very high. While in the bootstrapping phase, the number of protocol customers on board will likely be less than Sherlock's ideal customer count at scale. During this bootstrapping phase, it may be difficult to grow the staking pools as stakers will have less incentive to stake (due to low APY). This is the time when it will be critical to use SHER incentives to build up the pool. There are two main ways Sherlock can use SHER to build up funds in the staking pools:

1. Paying SHER to the staker pools in order to increase the effective APY on staking and encourage more stakers.
2. Selling a small amount of SHER for ETH or another token. Sherlock governance would then stake that ETH into the staking pools. This is effectively protocol-controlled value (as it’s come to be known). Sherlock governance may decide to put these funds into a “first-money-out” pool in order to encourage stakers even more. Stakers would then be protected from losses by the “first-money-out” pool in addition to any protection received from deductibles provided by protocols themselves.
