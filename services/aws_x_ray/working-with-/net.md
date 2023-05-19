---
id: Working with .NET
title: Working with .NET
created: 1683841041000
updated: 1683841041000
---
# Working with .NET

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-xray-developer-guide.git)
{% endhint %}

## X-Ray SDK for .NET

- **Note**  
The X\-Ray SDK for \.NET is an open source project\. You can follow the project and submit issues and pull requests on GitHub: [github\.com/aws/aws\-xray\-sdk\-dotnet](https://github.com/aws/aws-xray-sdk-dotnet)
- **Note**  
On Lambda, the X\-Ray SDK is optional\. If you don't use it in your function, your service map will still include a node for the Lambda service, and one for each Lambda function\. By adding the SDK, you can instrument your function code to add subsegments to the function segment recorded by Lambda\. See [AWS Lambda and AWS X\-Ray](xray-services-lambda.md) for more information\.

