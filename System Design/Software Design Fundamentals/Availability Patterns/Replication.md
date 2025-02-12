![[Pasted image 20250204125926.png]]
# Parent-Child
---
There is a main server that takes in both read/write traffic. The child servers replicate data that is written to the main server, and serve additional read-only traffic.
## Trade-offs
---
* Additional logic is needed to promote a child server to a parent server, in the case of a failure.
* There is a potential for loss of data if the parent fails before any newly written data can be replicated to other nodes.
* Writes are replayed to the read replicas. If there are a lot of writes, the read replicas can get bogged down with replaying writes and can't do as many reads.
* The more read child servers you have, the more you have to replicate, which leads to greater replication lag.
* On some systems, writing to the master can spawn multiple threads to write in parallel, whereas read replicas only support writing sequentially with a single thread.


![[Pasted image 20250204140736.png]]
# Master-Master
---
There are multiple servers that take both read/write server. A replication service syncs data across both servers.

## Trade-offs
---
* You'll need a load balancer or you'll need to make changes to your application logic to determine where to write.
* Most master-master systems are either loosely consistent (violating ACID) or have increased write latency due to synchronization.
* Conflict resolution comes more into play as more write nodes are added and as latency increases.