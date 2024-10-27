# Fix Review Process

The Lead Senior Watson for a contest will be expected to complete the fix review as a part of their role. The fix review ensures that the protocol’s changes post-audit have been properly implemented. The protocol will select a date within 3 weeks of the audit end-date for which they would like the fix review to be conducted. At this point one of 3 things happen:

1. Lead Senior Watson confirms that date works.
2. Lead Senior Watson proposes an alternative date for the fix review.
3. Lead Senior Watson does not have reasonable availability, and loses 25% of their fixed-pay compensation. That 25% will be used to compensate a new Watson (based on performance in that specific contest) to conduct the fix-review.

If the Lead Senior Watson determines that the protocol’s code changes require >1 day to review, then Sherlock will work with the protocol team to schedule a new (hopefully smaller) contest to review these changes. The new contest can be as short as 3 days or as long as 3 weeks. When it’s determined that the protocol’s code needs a new contest, the initial Lead Senior Watson will lose their 25% fixed pay for the fix review (which did not occur), but they will get first priority to be the Lead Senior Watson on that protocol’s follow-up contest (and receive fixed pay for that). The protocol will be able to put that refunded portion (25%) of the Lead Senior Watson’s pay towards the fixed pay for the Lead Senior in that follow-up contest. The fixed pay for the follow-up contest should always be equal to or greater than the 25% fixed pay that was withheld in the previous contest.&#x20;

{% hint style="info" %}
If a Lead Senior Watson places outside of the top 10 in the ranking for a contest they lead, then they must forfeit 25% of their fixed pay so that Sherlock can bring in a Watson who found more of the issues to conduct the fix review.&#x20;
{% endhint %}

### Receiving the 25% Fixed Pay

The 25% Fixed Pay will be released up to two weeks after the fix review occurs.

The two-week delay is so that the [Pre-Launch Bounty](../../bug-bounties/pre-launch-bounty.md) can flag any Critical issue that should have been caught in the fix review.

If no issues are reported that should have been caught in the fix review, the 25% fixed pay gets unlocked.

If an issue is reported that could have been caught during the original audit or audit contest, then it is not the sole responsibility of the fix reviewer to catch, and thus the 25% fixed pay gets unlocked.

If a Critical vulnerability is found that could only have been caught during the fix review (was introduced after the original audit), then, depending on the size of the Pre-Launch Bounty, some or all of the 25% fixed pay will be re-routed to the bug bounty submitter, and away from the fix reviewer.&#x20;
