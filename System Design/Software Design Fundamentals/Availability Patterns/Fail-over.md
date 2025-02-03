![[Pasted image 20250203013516.png]]
# Active-passive
---
In this failover model, there is a standby copy of the active cloud. The standby cloud, or health check service, will repeatedly ping the active servers to check for proper health. If the active cloud is showing issues, traffic will be redirected to the standby cloud.

The length of downtime is determined by whether the passive server is already running in 'hot' standby or whether it needs to start up from 'cold' standby. Only the active server handles traffic.

Active-passive failover can also be referred to as master-slave failover.

# Active-active
---
In this failover model, there are multiple active clouds handling traffic. They will share the traffic load between both clouds

If the servers are public-facing, the DNS would need to know about the public IPs of both servers. If the servers are internal-facing, application logic would need to know about both servers.

Active-active failover can also be referred to as master-master failover.

# Drawbacks
---
* Implementing failover adds additional complexity and resources to the system
* In Active-passive failover, there is always a chance that there will be lost data if the active cloud fails before data is synced into the passive cloud

# Further Reading
---
* [Active Passive & Active Active Architecture for High Availability System](https://www.geeksforgeeks.org/active-passive-active-active-architecture-for-high-availability-system/)
* [Failover Patterns - System Design](https://www.geeksforgeeks.org/failover-patterns-system-design/#what-is-the-failover-pattern)
* [Availability Patterns](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#availability-patterns)