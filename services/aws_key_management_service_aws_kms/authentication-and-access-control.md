---
id: Authentication and access control
title: Authentication and access control
created: 1683841041000
updated: 1683841041000
---
# Authentication and access control

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-kms-developer-guide.git)
{% endhint %}

## IAM policies

- **Note**  
To use an IAM policy to control access to a KMS key, the key policy for the KMS key must give the account permission to use IAM policies\. Specifically, the key policy must include the [policy statement that enables IAM policies](key-policy-default.md#key-policy-default-allow-root-enable-iam)\.  
This section explains how to use IAM policies to control access to AWS KMS operations\. For more general information about IAM, see the [IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.


## VPC endpoint

- **Note**  
AWS KMS supports VPC endpoint policies beginning in July 2020\. VPC endpoints for AWS KMS that were created before that date have the [default VPC endpoint policy](#vpce-default-policy), but you can change it at any time\.
- **Note**  
Use caution when creating key policies and IAM policies based on your VPC endpoint\. If a policy statement requires that requests come from a particular VPC or VPC endpoint, requests from integrated AWS services that use an AWS KMS resource on your behalf might fail\. For help, see [Using VPC endpoint conditions in policies with AWS KMS permissions](conditions-aws.md#conditions-aws-vpce)\.  
Also, the `aws:sourceIP` condition key is not effective when the request comes from an [Amazon VPC endpoint](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html)\. To restrict requests to a VPC endpoint, use the `aws:sourceVpce` or `aws:sourceVpc` condition keys\. For more information, see [Identity and access management for VPC endpoints and VPC endpoint services](https://docs.aws.amazon.com/vpc/latest/privatelink/vpc-endpoints-iam.html) in the *AWS PrivateLink Guide*\.


## Condition keys

- **Note**  
Condition key values must adhere to the character and encoding rules for AWS KMS key policies and IAM policies\. For details about key policy document rules, see [Key policy format](key-policy-overview.md#key-policy-format)\. For details about IAM policy document rules, see [IAM name requirements](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_iam-quotas.html#reference_iam-quotas-names) in the *IAM User Guide*\.\.


## Cross-account access

- **Note**  
The examples in this topic show how to use a key policy and IAM policy together to provide and limit access to a KMS key\. These generic examples are not intended to represent the permissions that any particular AWS service requires on a KMS key\. For information about the permissions that an AWS service requires, see the encryption topic in the service documentation\.
- **Note**  
The **key policy** for the KMS key must give the external account \(or users and roles in the external account\) permission to use the KMS key\.
- **Note**  
Do not set the Principal to an asterisk \(\*\) in any key policy statement that allows permissions unless you use conditions to limit the key policy\. An asterisk gives every identity in every AWS account permission to use the KMS key, unless another policy statement explicitly denies it\. Users in other AWS accounts just need corresponding IAM permissions in their own accounts to use the KMS key\.


## Permissions reference

- **Note**  
You might have to scroll horizontally or vertically to see all of the data in the table\.

