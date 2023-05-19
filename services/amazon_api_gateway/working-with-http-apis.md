---
id: Working with HTTP APIs
title: Working with HTTP APIs
created: 1683841041000
updated: 1683841041000
---
# Working with HTTP APIs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-api-gateway-developer-guide.git)
{% endhint %}

## Develop

- **Note**  
To invoke a Lambda integration, API Gateway must have the required permissions\. You can use a resource\-based policy or an IAM role to grant API Gateway permissions to invoke a Lambda function\. To learn more, see [AWS Lambda Permissions](https://docs.aws.amazon.com/lambda/latest/dg/lambda-permissions) in the * AWS Lambda Developer Guide*\.


## Monitor

- **Note**  
API Gateway might not generate logs and metrics in the following cases:  
413 Request Entity Too Large errors
Excessive 429 Too Many Requests errors
400 series errors from requests sent to a custom domain that has no API mapping
500 series errors caused by internal failures

