# Fetch Rewards
## New Structured Relational Data Model
![image](https://github.com/user-attachments/assets/aa6575bc-266c-41de-9e9f-941d182775a8)

## SQL queries
Queries for the following bullet points are available in the IPYNB
- What are the top 5 brands by receipts scanned for most recent month?
- How does the ranking of the top 5 brands by receipts scanned for the recent month compare to the ranking for the previous month?
- When considering average spend from receipts with 'rewardsReceiptStatus’ of ‘Accepted’ or ‘Rejected’, which is greater?
- When considering total number of items purchased from receipts with 'rewardsReceiptStatus’ of ‘Accepted’ or ‘Rejected’, which is greater?
- Which brand has the most spend among users who were created within the past 6 months?
- Which brand has the most transactions among users who were created within the past 6 months?

## Data Quality Issues
Data issues were identified during the exploration phase, primarily falling into the following categories:
- Validity
- Completeness
- Consistency
- Uniqueness

## Communicate with Stakeholders
After analyzing the data, here are some observations and questions:
- Out of 1119 receipts, only 679 have corresponding purchases. Should we retain records of receipts with no purchases, or should they be discarded?
- There are 91 receipts that were scanned but not accepted, yet the users still received points. What could be the reason for awarding points to these users?
- Four receipts were scanned and accepted, but no points were awarded, and the 'bonusPointsEarnedReason' is NULL for these cases. Is there a glitch in the evaluation or point-awarding process? It would be helpful to understand the actual reason for these instances.

Please note that several data issues were identified during the data exploration phase, primarily related to validity, completeness, consistency, and uniqueness. Additional details can be found [here](https://github.com/nav-01/fetch_rewards_exc/blob/main/fetch_rewards_nb.ipynb?short_path=82009f9#L1838).

Additionally, any insights or further information regarding the downstream usage and the specific questions this data is meant to address would be valuable for optimizing the data assets. For example, redundant data from the 'rewardsReceiptItemList' JSON and the 'Receipts' dataset could be removed during the data processing stage.

And finally, there may not be any performance concerns at the moment but an increase in data volume can affect both storage and query performance. To address this, we can leverage cloud data warehouses like Snowflake, AWS Redshift, BigQuery, etc., which offer easy scalability and data access without the need for managing physical infrastructure. Additionally, partitioning large datasets by specific date ranges can enhance query performance. It may also be beneficial to remove unnecessary columns or keys from the 'rewardsReceiptItemList' JSON. Finally, using data observability tools like Monte Carlo, DataDog, etc., can help identify bottlenecks, performance issues, and data quality concerns.

## Note:
Python Version = 3.11.5
