# Unstaking

## Unstake

Once the cooldown period ends, a 2-day window will open where the staker can unstake their lockTokens (both the original staked token and the staked SherX). They will call the unstake function which will receive their lockTokens and lockSherX and transfer the initial staked tokens (plus interest from Aave, Compound, etc.) and any SherX interest earned (post guarded launch).

## Recover

If a user does not unstake their lockTokens during the 2-day unstake window, the user must now call "recover" in order to get their lockTokens back from the contract (and continue accruing interest). After recover is called, the lockTokens are returned to the user and a new cooldown must be activated in order to try to unstake the funds again.

## Cancel

A user also has the option to cancel a cooldown period that has already begun. This action returns stakeTokens to the user so the user can continue earning interest.
