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


## Troubleshooting ECS Anywhere issues

- **Important**  
Amazon ECS provides the Amazon ECS logs collection tool\. You can use it to collect logs from your external instances for troubleshooting purposes\. For more information, see [Amazon ECS logs collector](ecs-logs-collector.md)\.


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


## Using Docker debug output

- **Important**  
This procedure is written for the Amazon ECS\-optimized Amazon Linux AMI\. For other operating systems, see [Enable debugging](https://docs.docker.com/engine/admin/#enable-debugging) and [Control and configure Docker with systemd]() in the Docker documentation\.


## Amazon ECS Log File Locations

- **Note**  
If you are not sure how to collect all of the logs on your container instances, you can use the Amazon ECS logs collector\. For more information, see [Amazon ECS logs collector](ecs-logs-collector.md)\.


## Amazon ECS logs collector

- **Note**  
The source code for the Amazon ECS logs collector is available on GitHub for both [Linux](https://github.com/awslabs/ecs-logs-collector) and [Windows](https://github.com/awslabs/aws-ecs-logs-collector-for-windows)\. We encourage you to submit pull requests for changes that you would like to have included\. However, Amazon Web Services doesn't currently support running modified copies of this software\.


## Agent introspection diagnostics

- **Important**  
Your container instance must have an IAM role that allows access to Amazon ECS in order to reach the introspection API\. For more information, see [Amazon ECS container instance IAM role](instance_IAM_role.md)\.
- **Note**  
The command below is piped through the python \-mjson\.tool for greater readability\.


## Docker diagnostics

- **Note**  
Docker logs are only available on the container instance if you are using the default `json` log driver\. If you have configured your tasks to use the `awslogs` log driver, then your container logs are available in CloudWatch Logs\. For more information, see [Using the awslogs log driver](using_awslogs.md)\.


## API failure reasons

- **Note**  
Besides the failure scenarios described here, APIs can also fail due to exceptions, resulting in error responses\. For a list of such exceptions, see [Common Errors](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/CommonErrors.html)\.

