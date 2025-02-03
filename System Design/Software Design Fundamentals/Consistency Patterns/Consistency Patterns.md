

# Comparison Table
---

|                  | Backups | Leader-Follower | Multi-Leader | 2 Phase Commits | Paxos      |
| ---------------- | ------- | --------------- | ------------ | --------------- | ---------- |
| **Constitency**  | Weak    | Eventual        | Eventual     | Strong          | Strong     |
| **Transactions** | No      | Full            | Local        | Full            | Full       |
| **Latency**      | Low     | Low             | Low          | High            | High       |
| **Throughput**   | High    | Hgih            | High         | Low             | Medium     |
| **Data Loss**    | Lots    | Some            | Some         | None            | None       |
| **Failover**     | Down    | Read only       | Read/Write   | Read/Write      | Read/Write |


# Further Readings
---
* [Consistency Patterns](https://systemdesign.one/consistency-patterns/)