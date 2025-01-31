#system-design 


![[Excalidraw/Drawing 2024-11-25 19.54.06.excalidraw.md|100%]]
## What is a load balancer?
---
The load balancer is a service that equally distributes work between multiple servers. The idea came about when horizontal scaling was introduced. We needed a way to guarantee that all the servers will get an equal amount of load, no matter how many servers we put, so that we could infinitely scale. 