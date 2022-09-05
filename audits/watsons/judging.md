# Judging

At the official end-date of the audit, Sherlock’s team will go through and de-duplicate issues, as well as judge every issue. Sherlock is exclusively focused on high and medium severity findings, as these are the types of vulnerabilities which will cause a loss of user funds and most materially damage the reputation of the protocols Sherlock seeks to protect.

**Criteria for Issues:**

**Medium:** There is a viable scenario (even if unlikely) that could cause the protocol to enter a state where a material amount of funds can be lost. The attack path is possible with assumptions that either mimic on-chain conditions or reflect conditions that have a reasonable chance of becoming true in the future. The more expensive the attack is for an attacker, the less likely it will be included as a Medium (holding all other factors constant). The vulnerability must be something that is not considered an acceptable risk by a reasonable protocol team.

**High:** This vulnerability would result in a material loss of funds and the cost of the attack is low (relative to the amount of funds lost). The attack path is possible with reasonable assumptions that mimic on-chain conditions. The vulnerability must be something that is not considered an acceptable risk by a reasonable protocol team.

### **Case Law**

\
**Could Denial-of-Service (DOS), griefing, or locking of contracts count as a Medium (or High) issue?**

It would not count if the DOS, etc. lasts a known, finite amount of time <1 year. If it will result in funds being inaccessible for >=1 year, then it would count as a loss of funds and be eligible for a Medium or High designation. The greater the cost of the attack for an attacker, the less severe the issue becomes.&#x20;
