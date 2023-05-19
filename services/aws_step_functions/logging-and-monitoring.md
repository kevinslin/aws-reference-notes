---
id: Logging and monitoring
title: Logging and monitoring
created: 1683841041000
updated: 1683841041000
---
# Logging and monitoring

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## Amazon CloudWatch Metrics

- **Note**  
Lambda Function Metrics are emitted for Task states that specify the Lambda function ARN in the ` Resource` field\. Task states that use `"Resource": "arn:aws:states:::lambda:invoke"` emit Service Integration Metrics instead\. For more information, see [Invoke Lambda with Step Functions](connect-lambda.md)\.


## Logging using CloudWatch Logs

- **Note**  
When you configure logging, [CloudWatch Logs charges](http://aws.amazon.com/cloudwatch/pricing) will apply\.

