# Basic CRUD Service
---

![[CRUD Service.png]]
*This design preemptively handles some of the common issues with high scale traffic. The load balancing prevents a hot partition in the primary service. The cached will also help in preventing hot database records by storing the data for less computing cost and better read performance. The design can be utilized in most scenarios since most services can be reduced to this.*


# Async Job Service
---

![[Async Job Service.png]]
*The design can be used when you have high processing traffic that allows for some delay in processing. It also can be utilized when you need the system to be event driven. This design can excel when there is an extreme amount of traffic, where each unit of traffic has high processing costs.*


# Two Stage Architecture
---

![[Two Stage Architecture.png]]
