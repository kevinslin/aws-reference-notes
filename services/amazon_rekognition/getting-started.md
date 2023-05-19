---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rekognition-developer-guide.git)
{% endhint %}

## Step 1: Set up an AWS account and create a User

- **Note**  
An IAM user with administrator permissions has unrestricted access to the AWS services in your account\. For information about restricting access to Amazon Rekognition operations, see [Amazon Rekognition identity\-based policies](security_iam_service-with-iam.md#security_iam_service-with-iam-id-based-policies)\. The code examples in this guide assume that you have a user with the `AmazonRekognitionFullAccess` permissions\. `AmazonS3ReadOnlyAccess` is required for examples that access images or videos that are stored in an Amazon S3 bucket\. The Amazon Rekognition Video stored video code examples also require `AmazonSQSFullAccess` permissions\. Depending on your security requirements, you might want to use an IAM group that's limited to these permissions\. For more information, see [Creating IAM Groups](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_create.html)\.

