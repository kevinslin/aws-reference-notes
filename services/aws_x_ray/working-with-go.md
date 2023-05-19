---
id: Working with Go
title: Working with Go
created: 1683841041000
updated: 1683841041000
---
# Working with Go

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-xray-developer-guide.git)
{% endhint %}

## X-Ray SDK for Go

- **Note**  
On Lambda, the X\-Ray SDK is optional\. If you don't use it in your function, your service map will still include a node for the Lambda service, and one for each Lambda function\. By adding the SDK, you can instrument your function code to add subsegments to the function segment recorded by Lambda\. See [AWS Lambda and AWS X\-Ray](xray-services-lambda.md) for more information\.

