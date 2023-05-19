---
id: Security in Secrets Manager
title: Security in Secrets Manager
created: 1683841041000
updated: 1683841041000
---
# Security in Secrets Manager

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-secrets-manager-docs.git)
{% endhint %}

## Mitigate the risks of using the AWS CLI to store your AWS Secrets Manager secrets

- **Important**  
By default, you can't perform an equivalent technique in Windows unless you first reduce the size of the command history buffer to **1**\.


## Secret encryption and decryption

- **Note**  
In the past, Secrets Manager validation requests did not include an encryption context\. You might find calls with no encryption context in older AWS CloudTrail logs\.

