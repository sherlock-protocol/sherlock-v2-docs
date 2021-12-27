# Claims Process

One of Sherlock's biggest strengths is its fully trustless, unbiased claims process.&#x20;

If an exploit is thought to have occurred at a covered protocol, the protocol will submit a claim to Sherlock.&#x20;

The Watsons responsible for this protocol will first work alongside the core devs to mitigate the exploit.&#x20;

Once the exploit has been mitigated, the Watsons will work to understand the exploit's cause and magnitude. Through this process, a protocol will have a good sense of whether the exploit experienced is covered by Sherlock, and thus a claim should be submitted. The Watsons will help with the general claim submission process as well as choosing the correct timestamp and amount that should be submitted.

The first stage of evaluating a claim is the committee vote of the SPCC (Sherlock Protocol Claims Committee). The SPCC is made up of members of the core team of Sherlock as well as security advisors to Sherlock. These committee members will be well-versed in the nature of exploits covered by Sherlock. All of the members of the SPCC have a stake in Sherlock and an interest in doing what's best for the long-term success of Sherlock. They will also have reputations and public identities outside of Sherlock that they will want to uphold. These factors will make it very likely that the members of the SPCC will see it in their best interest to make the most accurate claims decision possible.

![](https://i.imgur.com/MDFJCCt.png)

The decision made by the SPCC will be binary (either the claim will be paid out or not). Once a decision is made on a claim by the SPCC, there are a few possible paths.&#x20;

The first path for a covered protocol is to agree and accept the SPCC's decision.&#x20;

The second path is to revise the claim (i.e. the amount of the claim) and re-submit.&#x20;

The third and last path is to escalate the claim to the UMA Optimistic Oracle. This would require the covered protocol to “stake” a reasonable claim amount (i.e. $5k) to escalate the claim above the SPCC. The escalation would move the claim decision from Sherlock’s hands into the hands of UMA’s [Optimistic Oracle](https://docs.umaproject.org/getting-started/oracle). The claims decision would then be voted on by UMA tokenholders using UMA’s Data Verification Mechanism and the resolution of that vote is the final claim decision. If the covered protocol is proven correct, then the amount specified by the claim will be paid out. They will also receive the stake amount back in full. If the covered protocol's escalation is not successful, then the amount specified by the claim is not paid out and the stake amount is not returned.

Note: There is also an option for an UMA multisig to reject the claim decision if the core UMA team collectively believes the oracle didn't function properly. Because the UMA Optimistic Oracle is still somewhat new to this use case, and because the dollar amounts at stake could be extremely high, Sherlock has included this intermediate step in the code with the option to enable or disable it at launch. Once disabled, it cannot be re-enabled.&#x20;
