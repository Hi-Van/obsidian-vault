![[Pasted image 20250131135837.png]]

# What is a Data Service 
---
A data service is a microservice who's exclusive responsibility is to retrieve data from the database.
This helps with preventing one database from inheriting too much traffic by creating subscription events to publish data, which is also known as request coalescing. This works by the following event:

1. The data service receives traffic to request data from the server
2. The data service creates a subscription event for the data request
	1. If there are repeated duplicate requests from traffic, then subscribe them to the same data retrieval event
3. Once the subscription event retrieves the data, send the data to every request that is subscribed to it

# Further Reading
---
* [How Discord solved the Hot partition problem](https://engineeringatscale.substack.com/p/how-discord-solved-hot-partition-problem)