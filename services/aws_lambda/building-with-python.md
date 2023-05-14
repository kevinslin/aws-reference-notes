---
id: Building with Python
title: Building with Python
created: 1683841041000
updated: 1683841041000
---
# Building with Python

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}

## Handler

- **Note**  
In Python 3\.9 and later releases, Lambda includes the requestId of the invocation in the error response\.


## Deploy .zip file archives

- **Note**  
A python package may contain initialization code in the \_\_init\_\_\.py file\. Prior to Python 3\.9, Lambda did not run the \_\_init\_\_\.py code for packages in the function handler’s directory or parent directories\. In Python 3\.9 and later releases, Lambda runs the init code for packages in these directories during initialization\.   
Note that Lambda runs the init code only when the execution environment is first initialized, not for each function invocation in that initialized environment\.


## Tracing

- **Important**  
**ADOT is the preferred method for instrumenting your Lambda functions**\. We recommend using ADOT for all new applications\. However, due to the flexibility OpenTelemetry offers, your Lambda function invocations may experience cold start latency increases\. If you're optimizing for low\-latency and also do not require OpenTelemetry's advanced capabilities such as telemetry correlation and dynamically configurable backend destinations, you may want to use the AWS X\-Ray SDK over ADOT\.
- **Note**  
You cannot configure the X\-Ray sampling rate for your functions\.

