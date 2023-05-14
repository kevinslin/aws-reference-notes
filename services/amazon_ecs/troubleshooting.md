---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ecs-developer-guide.git)
{% endhint %}

## Using Amazon ECS Exec for debugging

- **Note**  
This configuration only handles the logging of the `execute-command` session\. It doesn't affect logging of your application\.
- **Note**  
Because the `execute-command` API action contains only task and cluster resources in a request, only cluster and task tags are evaluated\.


## Checking stopped tasks for errors

- **Important**  
Stopped tasks only appear in the Amazon ECS console, AWS CLI, and AWS SDKs for at least 1 hour after the task stops\. After that, the details of the stopped task expire and aren't available in Amazon ECS\.  
Amazon ECS also sends task state change events to Amazon EventBridge\. You can't view events in EventBridge\. Instead, you create rules to send the events to other persistent storage such as Amazon CloudWatch Logs\. You can use the storage to view your stopped task details after it has expired from view in the Amazon ECS console\. For more information, see [Task state change events](ecs_cwe_events.md#ecs_task_events)\.  
For a sample EventBridge configuration to archive Amazon ECS events to Amazon CloudWatch Logs, see [ECS Stopped Tasks in CloudWatch Logs](https://github.com/aws-samples/amazon-ecs-stopped-tasks-cwlogs#ecs-stopped-tasks-in-cloudwatch-logs) on the GitHub website\.


## Invalid CPU or memory value specified

- **Note**  
When using Terraform, the following error may be returned\.
- **Note**  
Task\-level CPU and memory parameters are ignored for Windows containers\.


## API failure reasons

- **Note**  
Besides the failure scenarios described here, APIs can also fail due to exceptions, resulting in error responses\. For a list of such exceptions, see [Common Errors](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/CommonErrors.html)\.

