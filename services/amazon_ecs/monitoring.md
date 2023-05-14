---
id: Monitoring
title: Monitoring
created: 1683841041000
updated: 1683841041000
---
# Monitoring
{% hint style="info" %}
This page was generated from content adapted from [Dummy](https://docs.aws.amazon.com/ec2/index.html)
{% endhint %}
## CloudWatch metrics

- **Note**  
You can disable CloudWatch metrics collection by setting `ECS_DISABLE_METRICS=true` in your Amazon ECS container agent configuration\. For more information, see [Amazon ECS container agent configuration](ecs-agent-config.md)\.
- **Note**  
If you're using tasks with the EC2 launch type and have Linux container instances, the Amazon ECS container agent relies on Docker `stats` metrics to gather CPU and memory data for each container running on the instance\. For burstable performance instances \(T3, T3a, and T2 instances\), the CPU utilization metric may reflect different data compared to instance\-level CPU metrics\.
- **Note**  
In this example, the CPU utilization will only go above 100% when the CPU units are defined at the container level\. If you define CPU units at the task level, the utilization will not go above the defined task\-level limit\.


## CloudWatch Container Insights

- **Important**  
Metrics collected by CloudWatch Container Insights are charged as custom metrics\. For more information about CloudWatch pricing, see [CloudWatch Pricing](https://aws.amazon.com/cloudwatch/pricing/)\. Amazon ECS also provides monitoring metrics that are provided at no additional cost\. For more information, see [Amazon ECS CloudWatch metrics](cloudwatch-metrics.md)\.
- **Important**  
For clusters containing tasks or services using the EC2 launch type, your container instances must be running version 1\.29\.0 or later of the Amazon ECS agent\. For more information, see [Amazon ECS Linux container agent versions](ecs-agent-versions.md)\.


## Collecting application trace data

- **Important**  
If you're also collecting application metrics using the AWS Distro for OpenTelemetry integration, ensure your task IAM role also contains the permissions necessary for that integration\. For more information, see [Collecting application metrics](metrics-data.md)\.


## Logging Amazon ECS API calls with AWS CloudTrail

- **Note**  
These examples have been formatted for improved readability\. In a CloudTrail log file, all entries and events are concatenated into a single line\. In addition, this example has been limited to a single Amazon ECS entry\. In a real CloudTrail log file, you see entries and events from multiple AWS services\.

