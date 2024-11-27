#system-design 

![[Drawing 2024-11-25 19.06.40.excalidraw|100%]]

##  What is Horizontal Scaling?
---
This refers to the act of adding more servers to a system instead of making each individual server more powerful. For example, if you host a service on a single server and it is getting overrun by traffic, you would horizontally scale by adding two more servers to your service that you are able to utilize. To put it in a more relatable context, imagine you're working on a group project in school. If you find that your current workload is too large for each team member, you might want to recruit more team members to give a smaller workload to each individual within the group.

## Why would we choose this over vertical scaling?
---
There is a technological limit to vertical scaling. Sometimes we already are utilizing the best CPU that we can get on the server. There's simply nothing better that we can currently get. In this case, we would rather gather more resources than try to upgrade the current resources that we have. To bring it back to the previous context, sometimes you already have the smartest people in your group. In order to handle more workload, you can't just get smarter people. They're not available. Sometimes you need to get more people and then chunk up the work into smaller sizes for each individual within the group.

## Common Issues and Trade Offs
---
There comes a common issue when introducing more servers into a system. Just because you add more servers doesn't mean each server will get an equal amount of load. We can encounter a scenario where all the work goes to one server and none of the other servers get anything. We will have to introduce [[Load Balancers & Caches|load balancers]], which will attempt to distribute the work evenly and thus prevent a single server from overloading.
