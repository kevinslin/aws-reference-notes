---
id: Building with Go
title: Building with Go
created: 1683841041000
updated: 1683841041000
---
# Building with Go
{% hint style="info" %}
This page was generated from content adapted from [Dummy](https://docs.aws.amazon.com/ec2/index.html)
{% endhint %}
## Deploy .zip file archives

- **Note**  
If you have not already done so, you must install [git](https://git-scm.com/) and then add the `git` executable to your Windows `%PATH%` environment variable\.
- **Note**  
When you create a Go Lambda function using the AWS CLI, the value of the handler setting you define is the executable file name\. For more information, see [AWS Lambda function handler in Go](golang-handler.md)\.


## Tracing

- **Important**  
**ADOT is the preferred method for instrumenting your Lambda functions**\. We recommend using ADOT for all new applications\. However, due to the flexibility OpenTelemetry offers, your Lambda function invocations may experience cold start latency increases\. If you're optimizing for low\-latency and also do not require OpenTelemetry's advanced capabilities such as telemetry correlation and dynamically configurable backend destinations, you may want to use the AWS X\-Ray SDK over ADOT\.
- **Note**  
You cannot configure the X\-Ray sampling rate for your functions\.

