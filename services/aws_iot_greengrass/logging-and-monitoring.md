---
id: Logging and monitoring
title: Logging and monitoring
created: 1683841041000
updated: 1683841041000
---
# Logging and monitoring

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Monitor Greengrass logs

- **Note**  
The Greengrass core device's token exchange role must allow the core device to write to CloudWatch Logs, as shown in the following example IAM policy\. If you [installed the AWS IoT Greengrass Core software with automatic resource provisioning](quick-installation.md), your core device has these permissions\.


## Get deployment and component health status notifications

- **Note**  
Amazon EventBridge is an event bus service that you can use to connect your applications with data from a variety of sources, such as [Greengrass core devices](telemetry.md) and deployment and component notifications\. For more information, see [What is Amazon EventBridge?](https://docs.aws.amazon.com/eventbridge/latest/userguide/what-is-amazon-eventbridge.html) in the *Amazon EventBridge User Guide*\.
- **Note**  
To allow Amazon EventBridge to call your target topic, you must add a resource\-based policy to your topic\. For more information, see [Amazon SNS permissions](https://docs.aws.amazon.com/eventbridge/latest/userguide/resource-based-policies-eventbridge.html#sns-permissions) in the *Amazon EventBridge User Guide*\.


## Check core device status

- **Note**  
AWS IoT Greengrass relies on individual devices to send status updates to the AWS Cloud\. If the AWS IoT Greengrass Core software isn't running on the device, or if device isn't connected to the AWS Cloud, then the reported status of that device might not reflect its current status\. The status timestamp indicates when the device status was last updated\.  
Core devices send status updates at the following times:  
When the AWS IoT Greengrass Core software starts
When the core device receives a deployment from the AWS Cloud
When the status of any component on the core device becomes `BROKEN`
At a [regular interval that you can configure](greengrass-nucleus-component.md#greengrass-nucleus-component-configuration-fss), which defaults to 24 hours
For AWS IoT Greengrass Core v2\.7\.0, the core device sends status updates when local deployment and cloud deployment occurs

