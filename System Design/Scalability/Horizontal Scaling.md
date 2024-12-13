#system-design 

![[Drawing 2024-11-25 19.06.40.excalidraw|100%]]

##  What is Horizontal Scaling?
---
This refers to the act of adding more servers to a system instead of making each individual server more powerful. For example, if you host a service on a single server and it is getting overrun by traffic, you would horizontally scale by adding two more servers to your service that you are able to utilize. 

## Why would we choose this over vertical scaling?
---
There is a technological limit to vertical scaling. Sometimes we already are utilizing the best CPU that we can get on the server. There's simply nothing better that we can currently get. In this case, we would rather gather more resources than try to upgrade the current resources that we have.

## Common Issues and Trade Offs
---
There comes a common issue when introducing more servers into a system. Just because you add more servers doesn't mean each server will get an equal amount of load. We can encounter a scenario where all the work goes to one server and none of the other servers get anything. We will have to introduce [[Load Balancers & Caches|load balancers]], which will attempt to distribute the work evenly and thus prevent a single server from overloading.

Another issue arises where sessions cannot be shared among server instances. While client may have a session on server A, it is not guaranteed to also exist on server B. Therefore, we must over come this issue in 3 ways:

1. Sessions can be stored client side
	1. `localStorage` API in many modern web browsers
	2. `Cookie` header in HTTP requests and browser storage
2. Sessions can be stored where all traffic is guaranteed to travel
	1. [In-memory](https://en.wikipedia.org/wiki/Volatile_memory#:~:text=Volatile%20memory%2C%20in%20contrast%20to,uses%20including%20as%20primary%20storage.) within the load balancer or API gateway
3. Sessions can be stored in a sharable resource
	1. Within database storage

