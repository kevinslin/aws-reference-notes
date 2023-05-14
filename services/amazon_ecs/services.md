---
id: Services
title: Services
created: 1683841041000
updated: 1683841041000
---
# Services
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ecs-developer-guide.git)
{% endhint %}
## Service load balancing

- **Note**  
When you use tasks sets, all the tasks in the set must all be configured to use Elastic Load Balancing or to not use Elastic Load Balancing\.


## Service throttle logic

- **Important**  
Tasks that are stopped after they reach the `RUNNING` state don't start the throttle logic or the associated service event message\. For example, assume that failed Elastic Load Balancing health checks for a service cause a task to be flagged as unhealthy, and Amazon ECS deregisters it and stops the task\. At this point, the tasks aren't throttled\. Even if a task's container command immediately exits with a non\-zero exit code, the task already moved to the `RUNNING` state\. Tasks that fail immediately because command errors don't cause the throttle or the service event message\.

