---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-xray-developer-guide.git)
{% endhint %}

## Data protection

- **Note**  
AWS KMS charges when X\-Ray uses a KMS key to encrypt or decrypt trace data\.  
**Default encryption** – Free\.
**AWS managed key** – Pay for key use\.
**customer managed key** – Pay for key storage and use\.
See [AWS Key Management Service Pricing](https://aws.amazon.com/kms/pricing/) for details\.
- **Note**  
 X\-Ray insights notifications sends events to Amazon EventBridge, which does not currently support customer managed keys\. For more information, see [Data Protection in Amazon EventBridge](https://docs.aws.amazon.com/eventbridge/latest/userguide/data-protection.html)\.
- **Note**  
X\-Ray does not support asymmetric KMS keys\.

