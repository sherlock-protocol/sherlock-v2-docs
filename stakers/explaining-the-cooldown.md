# Explaining the Cooldown

A staker will not be able to unstake immediately. This is because it will take Sherlock time to recognize, diagnose and pay out a hack. A staker could easily unstake their stake during this time as soon as they hear about a hack. Because of this dynamic, a cooldown period needs to be implemented before a staker can unstake. Currently the cooldown period is 7 days. So if a staker wants to unstake, they begin the process by activating the cooldown. This will start a 7-day timer in which a staker’s funds no longer earn interest (even though they are still exposed to hacks during this time).

To implement this, the staker’s lockTokens are transferred to the Sherlock protocol and earned interest goes to the “first money out” pool instead of the staker. After the 7-day cooldown expires, a staker will have a 2-day window to unstake. The same dynamic of being exposed to hacks but not receiving interest will apply for those 2 days. If a staker does not withdraw in that 2-day period then the staker must call the unstakeWindowExpiry() function in order to get their lockTokens back and continue earning interest. The staker will then have to restart the 7-day cooldown if they want to try to unstake again.

## Why doesn’t a staker get paid interest during the cooldown even though their funds are at risk?

There are two forces at work here:

1. There needs to be a disincentive for activating the cooldown. Otherwise, as a staker, it would make sense to repeatedly activate the cooldown (every 9 days in this example) to try to “game” the system and time your unstaking to avoid paying out future hacks.
2. From a technical implementation perspective, not paying interest during this period is much simpler (as opposed to solutions that include paying out interest during the cooldown). We've chosen this route for our V1 protocol design.
