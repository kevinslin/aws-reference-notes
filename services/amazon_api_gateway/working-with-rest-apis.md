---
id: Working with REST APIs
title: Working with REST APIs
created: 1683841041000
updated: 1683841041000
---
# Working with REST APIs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-api-gateway-developer-guide.git)
{% endhint %}

## Monitor

- **Note**  
API Gateway might not generate logs and metrics in the following cases:  
413 Request Entity Too Large errors
Excessive 429 Too Many Requests errors
400 series errors from requests sent to a custom domain that has no API mapping
500 series errors caused by internal failures
API Gateway will not generate logs and metrics when testing a REST API method\. The CloudWatch entries are simulated\. For more information, see [Use the API Gateway console to test a REST API method](how-to-test-method.md)\.

