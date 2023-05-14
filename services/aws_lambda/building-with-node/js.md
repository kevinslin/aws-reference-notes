---
id: Building with Node.js
title: Building with Node.js
created: 1683841041000
updated: 1683841041000
---
# Building with Node.js
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}
## Tracing

- **Important**  
**ADOT is the preferred method for instrumenting your Lambda functions**\. We recommend using ADOT for all new applications\. However, due to the flexibility OpenTelemetry offers, your Lambda function invocations may experience cold start latency increases\. If you're optimizing for low\-latency and also do not require OpenTelemetry's advanced capabilities such as telemetry correlation and dynamically configurable backend destinations, you may want to use the AWS X\-Ray SDK over ADOT\.
- **Note**  
You cannot configure the X\-Ray sampling rate for your functions\.

