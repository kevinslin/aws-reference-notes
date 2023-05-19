---
id: Ingesting data to AWS IoT SiteWise
title: Ingesting data to AWS IoT SiteWise
created: 1683841041000
updated: 1683841041000
---
# Ingesting data to AWS IoT SiteWise

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-sitewise-user-guide.git)
{% endhint %}

## Using AWS IoT Core rules

- **Note**  
When you send data to AWS IoT SiteWise with the rule action, your data must meet all of the requirements of the `BatchPutAssetPropertyValue` operation\. For example, your data can't have a timestamp earlier than 7 days from current Unix epoch time\. For more information, see [Ingesting data with the AWS IoT SiteWise API]()\.
- **Important**  
If your timestamp is a string, has a decimal portion, or isn't in seconds, AWS IoT SiteWise rejects the request\. You must convert the timestamp to seconds and nanosecond offset\. Use features of the AWS IoT rules engine to convert the timestamp\. For more information, see the following:  
[Getting timestamps for devices that don't report accurate time](#rule-timestamp-function)
[Converting timestamps that are in string format](#rule-time-to-epoch-function)
- **Note**  <a name="substitution-template-limitations"></a>
Because an expression in a substitution template is evaluated separately from the `SELECT` statement, you can't use a substitution template to reference an alias created using an `AS` clause\. You can reference only information present in the original payload, in addition to supported functions and operators\.
- **Note**  
The `time_to_epoch` function supports up to millisecond\-precision timestamp strings\. To convert strings with microsecond or nanosecond precision, you can configure an AWS Lambda function that your rule calls to convert the timestamp into numerical values\. For more information, see [Converting nanosecond\-precision timestamp strings](#rule-convert-precise-timestamp-string)\.
- **Note**  
This section contains advanced instructions that assume that you're familiar with how to create the following resources:  
Lambda functions\. For more information, see [Create a Lambda function with the console](https://docs.aws.amazon.com/lambda/latest/dg/getting-started-create-function.html) or [Using Lambda with the AWS CLI](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-awscli.html) in the *AWS Lambda Developer Guide*\.
AWS IoT rules with the AWS IoT SiteWise rule action\. For more information, see [Ingesting data using AWS IoT Core rules](#iot-rules)\.
- **Note**  
This solution invokes the Lambda function twice for each timestamp string\. You can create another rule to reduce the number of Lambda function invocations if your rule handles multiple data points that have the same timestamp in each payload\.  
To do so, create a rule with a republish action that invokes the Lambda and publishes the original payload with the timestamp string converted to `timeInSeconds` and `offsetInNanos`\. Then, create a rule with an AWS IoT SiteWise rule action to consume the converted payload\. With this approach, you reduce the number of times that the rule invokes the Lambda but increase the number of AWS IoT rule actions run\. Consider the pricing of each service if you apply this solution to your use case\.
- **Note**  
The above example includes a second slash \(`//`\) because AWS IoT removes the Basic Ingest prefix \(`$aws/rules/rule-name/`\) from the topic that's visible to the rule action\. In this example, the rule receives the topic `/company/windfarm/3/turbine/7/temperature`\.


## Using AWS IoT Greengrass stream manager

- **Note**  
To ingest data from OPC\-UA, Modbus TCP, and Ethernet/IP sources, you can configure a gateway that runs on AWS IoT Greengrass\. For more information, see [Ingesting data using a gateway](gateways.md)\.


## Using the AWS IoT SiteWise API

- **Important**  
The [BatchPutAssetPropertyValue](https://docs.aws.amazon.com/iot-sitewise/latest/APIReference/API_BatchPutAssetPropertyValue.html) operation is subject to the following quotas:

