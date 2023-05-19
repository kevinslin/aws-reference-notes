---
id: Programming the AWS KMS API
title: Programming the AWS KMS API
created: 1683841041000
updated: 1683841041000
---
# Programming the AWS KMS API

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-kms-developer-guide.git)
{% endhint %}

## Working with grants

- **Note**  
The `GranteePrincipal` field in the `ListGrants` response usually contains the grantee principal of the grant\. However, when the grantee principal in the grant is an AWS service, the `GranteePrincipal` field contains the [service principal](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html#principal-services), which might represent several different grantee principals\.

