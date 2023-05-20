---
id: Troubleshooting IAM
title: Troubleshooting IAM
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting IAM

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/iam-user-guide.git)
{% endhint %}

## Access denied error messages

- **Note**  
Some AWS services do not support this access denied error message format\. The content of access denied error messages can vary depending on the service making the authorization request\.
- **Note**  
When an SCP denies access, the error message can include the phrase `due to an explicit deny in a Service Control Policy`, even if the denial is implicit\.


## IAM policies

- **Note**  
By default, only the AWS account root user has access to all the resources in that account\. So if you are not signed in as the root user, you must have permissions granted by a policy\.
- **Note**  
IAM reviews service names, actions, and resource types for services that support policy summaries\. However, your policy summary might include a resource value or condition that does not exist\. Always test your policies with the [policy simulator](access_policies_testing-policies.md)\.
- **Note**  
IAM reviews service names, actions, and resource types for services that support policy summaries\. However, your policy summary might include a resource value or condition that does not exist\. Always test your policies with the [policy simulator](access_policies_testing-policies.md)\.
- **Note**  
As a [best practice](best-practices.md), we recommend that you use IAM Access Analyzer to validate your IAM policies to ensure secure and functional permissions\. We recommend that you open your existing policies and review and resolve any policy validation recommendations\.
- **Note**  
The policy engine does not allow such errors in new or edited policies\. However, the policy engine continues to permit policies that were saved before the engine was updated\. The behavior of existing policies with the error is as follows:  
Multiple `Effect` elements: only the last `Effect` element is observed\. The others are ignored\.
Multiple `Action` elements: all `Action` elements are combined internally and treated as if they were a single list\.
Multiple `Resource` elements: all `Resource` elements are combined internally and treated as if they were a single list\.
The policy engine does not allow you to save any policy with syntax errors\. You must correct the errors in the policy before you can save it\.We recommend that you review any correct any [policy validation](access_policies_policy-validator.md) recommendations for your policies\.

