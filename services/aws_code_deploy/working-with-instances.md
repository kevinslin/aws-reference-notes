---
id: Working with instances
title: Working with instances
created: 1683841041000
updated: 1683841041000
---
# Working with instances

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codedeploy-user-guide.git)
{% endhint %}

## Tagging instances for CodeDeploy deployments

- **Note**  
You can also include Amazon EC2 Auto Scaling groups in deployment groups, but they are identified by their names rather than by tags applied to instances\. For information, see [Integrating CodeDeploy with Amazon EC2 Auto Scaling](integrations-aws-auto-scaling.md)\.


## Instance health

- **Important**  
During a blue/green deployment, the deployment configuration and minimum healthy hosts value apply to instances in the replacement environment, not those in the original environment\. However, when instances in the original environment are deregistered from the load balancer, the overall deployment is marked as Failed if even a single original instance fails to be deregistered successfully\.
- **Note**  
CodeDeploy will attempt to deploy to all instances in a deployment group, even those that are currently in a Stopped state\. In the minimum healthy host calculation, a stopped instance has the same impact as a failed instance\. To resolve deployment failures due to too many stopped instances, either restart instances or change their tags to exclude them from the deployment group\.
- **Note**  
Make sure the minimum number of healthy instances you specify is less than the total number of instances in the deployment group\. If you specify a percentage value, remember it will be rounded up\. Otherwise, when the deployment starts, the number of healthy instances will already be less than or equal to the specified minimum number of healthy instances, and CodeDeploy will immediately fail the overall deployment\.

