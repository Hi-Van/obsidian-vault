![[Pasted image 20250131122338.png]]

# What is Database Partitioning
---
Database partitioning is the act of partitioning your data into separate databases based on a partitioning key. A partition key can be based on any column in the database, some examples include `created_timestamp`, `price`, `id_number`. The motivation behind this technique is to reduce the number of records in individual databases to hopefully improve read and write speeds. It also provides the benefit of fault tolerance, should one database partition fail, then other partitions should continue to be operable. A more advanced application of this technique can be observed through how discord stores it messages.

# Comparison of Benefits and Risks
---
## Pros

| Benefit              | Reason                                                                                               |
| -------------------- | ---------------------------------------------------------------------------------------------------- |
| Faster Queries       | Tables will typically contain less records after going through partitioning, leaving less operations |
| Improved Scalability | Through partitioning data, we can scale the number of databases we containing                        |
| Fault Isolation      | If one partition has issues, the rest of your database stays happy and healthy.                      |

## Cons

| Drawback         | Reason                                                                                                                                                                              |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Hot Partitioning | Even if we increase the number of partitions and databases, there is no guarantee that traffic will be split evenly. One database may become overly active when compared to others. |


# Further Reading
---
* [Scaling Databases - Part 5](https://python.plainenglish.io/scaling-databases-made-simple-part-5-lets-partition-the-data-cf5b62558d43)
* [How Discord Stores Messages](https://discord.com/blog/how-discord-stores-trillions-of-messages)