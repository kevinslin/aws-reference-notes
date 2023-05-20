---
id: Monitoring AWS IoT
title: Monitoring AWS IoT
created: 1683841041000
updated: 1683841041000
---
# Monitoring AWS IoT

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Configure AWS IoT logging

- **Note**  
Before you enable AWS IoT logging, make sure you understand the CloudWatch Logs access permissions\. Users with access to CloudWatch Logs can see debugging information from your devices\. For more information, see [Authentication and Access Control for Amazon CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/auth-and-access-control-cw.html)\.  
If you expect high traffic patterns in AWS IoT Core due to load testing, consider turning off IoT logging to prevent throttling\. If high traffic is detected, our service may disable logging in your account\.
- **Note**  
These documents were created for you when you created the logging role\. The documents have variables, `${partition}`, `${region}`, and `${accountId}`, that you must replace with your values\.
- **Note**  
You need the Amazon Resource Name \(ARN\) of the role that you want to use\. If you need to create a role to use for logging, see [Create a logging role](#create-logging-role) before continuing\.  
 The principal used to call the API must have [Pass role permissions](pass-role.md) for your logging role\.
- **Note**  
AWS IoT continues to support older commands \(set\-logging\-options and get\-logging\-options\) to set and get global logging on your account\. Be aware that when these commands are used, the resulting logs contain plain\-text, rather than JSON payloads and logging latency is generally higher\. No further improvements will be made to the implementation of these older commands\. We recommend that you use the "v2" versions to configure your logging options and, when possible, change legacy applications that use the older versions\.
- **Note**  
You need the Amazon Resource Name \(ARN\) of the role you want to use\. If you need to create a role to use for logging, see [Create a logging role](#create-logging-role) before continuing\.  
The principal used to call the API must have [Pass role permissions](pass-role.md) for your logging role\.


## Monitor AWS IoT using CloudWatch Logs

- **Note**  
The `AWSIotLogsV2` log group is not visible in the CloudWatch console until:  
You've enabled logging in AWS IoT\. For more info on how to enable logging in AWS IoT, see [Configure AWS IoT logging](configure-logging.md)
Some log entries have been written by AWS IoT operations\.


## Logging AWS IoT API calls using AWS CloudTrail

- **Note**  
AWS IoT data plane actions \(device side\) are not logged by CloudTrail\. Use CloudWatch to monitor these actions\.

