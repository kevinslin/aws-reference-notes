---
id: AWS Key Management Service
title: AWS Key Management Service
created: 1683841041000
updated: 1683841041000
---
# AWS Key Management Service

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-kms-developer-guide.git)
{% endhint %}

## Concepts

- **Note**  
AWS KMS is replacing the term *customer master key \(CMK\)* with *AWS KMS key* and *KMS key*\. The concept has not changed\. To prevent breaking changes, AWS KMS is keeping some variations of this term\.
- **Note**  
In May 2022, AWS KMS changed the rotation schedule for AWS managed keys from every three years \(approximately 1,095 days\) to every year \(approximately 365 days\)\.  
New AWS managed keys are automatically rotated one year after they are created, and approximately every year thereafter\.   
Existing AWS managed keys are automatically rotated one year after their most recent rotation, and every year thereafter\.
- **Note**  
When using the AWS KMS API, be careful about the key identifier that you use\. Different APIs require different key identifiers\. In general, use the most complete and practical key identifier for your task\.
- **Note**  
You cannot specify an encryption context in a cryptographic operation with an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) or an [HMAC KMS key](hmac.md)\. Asymmetric algorithms and MAC algorithms do not support an encryption context\.
- **Important**  
Because the encryption context is logged, it must not contain sensitive information\.

