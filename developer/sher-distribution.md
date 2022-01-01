## SHER Token Distribution manager

The goal of this contract is to distribute SHER tokens to stakers who stake their USDC into Sherlock (for a specified lockup period).

The core contract will call `pullReward(amount, period)` on every stake and restake action, and based on the curve described below the right amount of SHER tokens is sent back to the core contract.

Enough tokens need to be available in this contract to actually transfer them to the staker at the end of a lockup period.

### Kors curve

![SHER distribution curve](https://i.imgur.com/1U3ibuR.png)

The distribution curve starts with a fixed rate until a certain amount of TVL (a). Once (a) is reached, it will calculate rewards based on a linear slope until the max amount of TVL is reached (b).

For this curve the current TVL is used as the starting point, the `amount` being deposited is used to get the SHER rate for the user, and the period will function as a multiplier for the SHER rate.

So if you would receive 10 SHER tokens for a 1 month lockup, you would receive 30 SHER tokens for a 3 month lockup.

If tokens are being staked after the TVL is past (b), no SHER rewards are distributed.

### Design goal

The goal of this curve is to make sure Sherlock's TVL will never drop below a certain level. As the current TVL changes, the starting point on the curve moves more to the left if the TVL drops and to the right if the TVL increases. SHER rewards are automatically increased (on a TVL drop) or decreased (on a TVL increase) as the point on the slope changes.

The flat part is there for the situation where governance wants to have a predictable, fixed SHER distribution rate up until (a). Without the flat part we would distribute an excessive amount of SHER to the earliest stakers. The curve also has the flexilbity to remove the flat part completely by setting (a) to 0.

For simplicity we use the same curve for every staking `period` and use the `period` as a multiplier. This will result in the same APY for every staking period. But staking for 3 months twice or staking for 6 months once will likely result in a different SHER token reward as the point on the curve will likely be different when the second 3 month period is being initiated. It would be less SHER if the TVL is higher, it would be more SHER if the TVL is less after 3 months.
