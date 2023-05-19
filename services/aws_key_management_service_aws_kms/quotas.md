---
id: Quotas
title: Quotas
created: 1683841041000
updated: 1683841041000
---
# Quotas

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-kms-developer-guide.git)
{% endhint %}

## Resource quotas

- **Note**  
The [kms:ResourceAliases](conditions-kms.md#conditions-kms-resource-aliases) condition is effective only when the KMS key conforms to this quota\. If a KMS key exceeds this quota, principals who are authorized to use the KMS key by the `kms:ResourceAliases` condition are denied access to the KMS key\. For details, see [Access denied due to alias quota](abac.md#access-denied-alias-quota)\.
- **Note**  
The AWS KMS custom key store resource quota does not yet appear in the Service Quotas console\. You cannot view or manage this quota by using Service Quotas API operations\.


## Request quotas

- **Note**  
You might need to scroll horizontally or vertically to see all of the data in this table\.
- **Note**  
The AWS KMS custom key store request quota does not appear in the Service Quotas console\. You cannot view or manage this quota by using Service Quotas API operations\. To request a change in your custom key store request quota, visit the [AWS Support Center](https://console.aws.amazon.com/support/home) and create a case\.
- **Note**  
If the AWS CloudHSM cluster that is associated with the custom key store is processing numerous commands, including those unrelated to the custom key store, you might get an AWS KMS `ThrottlingException` at a lower\-than\-expected rate\. If this occurs, lower your request rate to AWS KMS, reduce the unrelated load, or use a dedicated AWS CloudHSM cluster for your custom key store\.


## Throttling requests

- **Note**  
AWS KMS custom key store quotas do not appear in the Service Quotas console\. You cannot view or manage these quotas by using Service Quotas API operations\. To request a change in your custom key store request quota, visit the [AWS Support Center](https://console.aws.amazon.com/support/home) and create a case\.

