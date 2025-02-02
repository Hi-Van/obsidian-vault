![[Pasted image 20250201182039.png]]

Eventual consistency is a consistency model employed in distributed systems where immediate consistency isn't a strict requirement. It guarantees that if no new updates are made, all nodes will eventually converge to the same data state. This approach is particularly useful in systems where high availability and performance are prioritized over absolute, real-time data synchronization. Here are some examples:

- **URL Shorteners:** When a short URL is created, the mapping between it and the original URL propagates to all servers. Due to eventual consistency, some servers might initially lack this mapping. However, within a short time, all servers will be updated, ensuring correct redirects. This temporary inconsistency allows for faster short URL creation.

- **Domain Name System (DNS):** DNS translates domain names to IP addresses. When a DNS record is updated, the change propagates throughout the distributed DNS system. Eventual consistency means different DNS servers might temporarily return different IP addresses for the same domain. Eventually, all servers will have the correct record. This temporary inconsistency is generally acceptable, as clients can retry with another DNS server.

- **Simple Mail Transfer Protocol (SMTP):** Email delivery relies on eventual consistency. When an email is sent, the sending server doesn't receive immediate confirmation of delivery. The email might be relayed through multiple servers, and temporary delays can occur. Ultimately, the email will be delivered (or bounced), but instant confirmation isn't guaranteed.

- **Object Storage (e.g., Amazon S3):** Uploaded objects are replicated across multiple locations. Eventual consistency means an object might not be immediately visible in all regions or availability zones after upload. Reads immediately following a write might return an older version. Eventually, the object becomes consistently available everywhere.

# Further Readings
---
* [Eventual Consistency in System Design](https://www.geeksforgeeks.org/eventual-consistency-in-distributive-systems-learn-system-design/)