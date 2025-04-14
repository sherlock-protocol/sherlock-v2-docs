## First Submitter Pod

Three percent of the total payouts will be reserved for a first-submitter pot, which is distributed among the first submitters of all valid issues.

The first submitter of any valid issue is determined by the timestamp of the last modification on the GitHub issue, across all issues within a valid issue family.

Each first submitter of an issue receives a number of shares from the first-submitter pot, based on the issue's severity and the number of duplicates it has.

The number of shares is calculated using the same formula as for determining issue shares, with the key difference being that only the first submitter of that issue family receives the shares:

> (First Submitter Shares) = (Severity Factor) * (0.9 ^ (IssueSubmissions - 1)) / IssueSubmissions

## Example

Consider a $100,000 contest with a $3,000 first-submitter pot, which includes 2 valid High-severity and 2 valid Medium-severity issues after final judging.

1. The first High-severity issue has 4 submissions in its family.  
   The first submitter will receive `5 * (0.9 ^ (4-1)) / 4 = 0.91125` shares for this issue.

2. The second High-severity issue is a solo submission.  
   The first submitter will receive `5 * (0.9 ^ (1-1)) / 1 = 5` shares for this issue.

3. The first Medium-severity issue has 2 submissions in its family.  
   The first submitter will receive `1 * (0.9 ^ (2-1)) / 2 = 0.45` shares for this issue.

4. The second Medium-severity issue has 4 submissions in its family.  
   The first submitter will receive `1 * (0.9 ^ (4-1)) / 4 = 0.18225` shares for this issue.

The percentage of the first-submitter pot each submitter receives is calculated by dividing the sum of their individual shares by the total number of shares awarded.

In this example, assume:  
- Alice was the first submitter of issue 1.  
- Frank was the first submitter of issue 2.  
- Bob was the first submitter of issue 3.  
- Dave was the first submitter of issue 4.  

The payouts for each would be:  
- Alice: $417.78  
- Bob: $206.31  
- Dave: $83.56  
- Frank: $2,292.35  

This example is further illustrated in [this spreadsheet](https://docs.google.com/spreadsheets/d/1eyyilZmwdjvZ2LaAsvDLzWyWKXDcqO9zabgNd2O5JWI/edit?usp=sharing).
