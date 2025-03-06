# Naive Design
---
![[Pasted image 20250304212455.png]]
*This design satisfies the user requirements at a minimal level. This will work for a fast proof of concept system, but will very quickly fail as client numbers scale.*

## Areas of Improvement
---
The primary service can forward a lot of repeated read traffic to the database, causing the database become a hot partition due to the same rows being repeatedly requested. This can be alleviated in several ways...

| Technique       | Explanation                                                                                                                                                                                                                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Push CDN        | A push-based CDN strategy will allow the primary service to read from the CDN resources and save database calls on repeated calls. We take a push-based approach because the short URLs should not change unless they expire or are manually edited, which can be written to the CDN while making the database transaction. |
| In-memory cache | This has a similar effect to the push CDN, where there is a different resource that has extremely high read performance and alleviates traffic load from the database.                                                                                                                                                      |
| Data Service    | This has the ability of request coalescence, where duplicate reads can be grouped into a single request event. This reduces the number of calls to the database from O(N) to O(K), N being the number of users and K being the number of unique keys, where K is typically much smaller than N.                             |

This design is also weaker in partial failure, as the read/write traffic will travel through a single service and they are not separated. If you separate the read and write traffic into individual services, it will allow users to continue to edit their short URLs, even if the redirection service is down. The relationship of service traffic also applies vice versa.


# My Design
---
![[Design URL Shortener.png]]
*This design attempts to iterate upon the naive approach by pre-emptively adding a strategy to mitigate read traffic. This design may focus a bit too much on consistency over availability. Availability should be the goal of this service.*


# Further Reading
---
* [Hello Interview Write Up - Bit.ly](https://www.hellointerview.com/learn/system-design/problem-breakdowns/bitly)
* [System Design Fight Club - TinyURL](https://systemdesignfightclub.com/tinyurl-revisited/)