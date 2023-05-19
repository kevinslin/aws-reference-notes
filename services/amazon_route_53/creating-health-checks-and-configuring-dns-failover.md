---
id: Creating health checks and configuring DNS failover
title: Creating health checks and configuring DNS failover
created: 1683841041000
updated: 1683841041000
---
# Creating health checks and configuring DNS failover

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-route53-docs.git)
{% endhint %}

## How Route 53 determines whether a health check is healthy

- **Note**  
Because Route 53 health checks monitor CloudWatch data streams instead of the state of CloudWatch alarms, you can't force the status of a health check to change by using the CloudWatch [SetAlarmState](https://docs.aws.amazon.com/AmazonCloudWatch/latest/APIReference/API_SetAlarmState.html) API operation\.


## Creating, updating, and deleting health checks

- **Important**  
If you're updating or deleting health checks that are associated with records, review the tasks in [Updating or deleting health checks when DNS failover is configured](health-checks-updating-deleting-tasks.md) before you proceed\.

