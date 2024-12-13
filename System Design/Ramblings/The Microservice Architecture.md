![[Excalidraw/Drawing 2024-11-26 19.18.11.excalidraw.md|100%]]

## What is a microservice?
---
A microservice refers to an individual service that is a smaller scale and holds a single responsibility. For example, instead of building the login functionality into the client API service from the diagram above, we would separate that specific functionality into a login service. This service would be called by the client API service whenever a client wishes to log into their accounts.

## Why use a microservice?
---
Microservices offer a way to separate specific "responsibilities" into their own individual services. This improves the maintainability of our repos by separating sections of code into smaller repositories. The microservice architecture also introduces other benefits:

* The ability to do live updates to endpoints by redeploying microservices at the same URL
* Improved Availability since a single microservice should not shut down an entire API
* Improved Partition Tolerance since microservices operate on different networks