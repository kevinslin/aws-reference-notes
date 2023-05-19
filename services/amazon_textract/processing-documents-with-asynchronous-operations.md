---
id: Processing Documents with Asynchronous Operations
title: Processing Documents with Asynchronous Operations
created: 1683841041000
updated: 1683841041000
---
# Processing Documents with Asynchronous Operations

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-textract-developer-guide.git)
{% endhint %}

## Calling Asynchronous Operations

- **Note**  
Before using this parameter, ensure you have the PutObject permission for the output bucket\. Additionally, ensure you have the Decrypt, ReEncrypt, GenerateDataKey, and DescribeKey permissions for the AWS KMS key if you decide to use it\.
- **Important**  
We don't recommend getting the request completion status by repeatedly calling the Amazon Textract `Get` operation\. This is because Amazon Textract throttles the `Get` operation if too many requests are made\. If you're processing multiple documents at the same time, it's simpler and more efficient to monitor one SQS queue for the completion notification than to poll Amazon Textract for the status of each job individually\.
- **Note**  
Results can be retrieved only up to 7 days of job initialization time\.


## Configuring Asynchronous Operations

- **Note**  
If you're using these instructions to set up the [Detecting or Analyzing Text in a Multipage Document](async-analyzing-with-sqs.md) example, you don't need to do steps 3 – 6\. The example includes code to create and configure the Amazon SNS topic and Amazon SQS queue\.

