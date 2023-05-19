---
id: Working with domains
title: Working with domains
created: 1683841041000
updated: 1683841041000
---
# Working with domains

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codeartifact-user-guide.git)
{% endhint %}

## Create a domain

- **Important**  
CodeArtifact supports only [symmetric KMS keys](https://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#symmetric-cmks)\. You can't use an [asymmetric KMS key](https://docs.aws.amazon.com/kms/latest/developerguide/symmetric-asymmetric.html#asymmetric-cmks) to encrypt your CodeArtifact domains\. For more information, see [Identifying symmetric and asymmetric KMS keys](https://docs.aws.amazon.com/kms/latest/developerguide/find-symm-asymm.html)\. To learn how to create a new customer managed key, see [Creating symmetric encryption KMS keys](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html#create-symmetric-cmk) in the *AWS Key Management Service Developer Guide*\.
CodeArtifact does not support AWS KMS External Key Stores \(XKS\)\. Attempting to create a domain with a key ARN that refers to an AWS KMS key in an external key store will fail with a 400 \(Bad Request\) error\.


## Domain policies

- **Note**  
A principal who wants to fetch packages from a repository endpoint must be granted the `ReadFromRepository` permission on the repository resource in addition to the `GetAuthorizationToken` permission on the domain\. Similarly, a principal who wants to publish packages to a repository endpoint must be granted the `PublishPackageVersion` permission in addition to `GetAuthorizationToken`\.   
For more information about the `ReadFromRepository` and `PublishPackageVersion` permissions, see [Repository Policies](repo-policies.md)\.
- **Note**  
You don't need to create a domain policy if a domain and all its repositories are owned by a single account and only need to be used from that account\.
- **Note**  
 You cannot grant permissions to another AWS account to update the resource policy on a domain using a resource policy, since the resource policy is ignored when calling put\-domain\-permissions\-policy\.


## Tag a domain

- **Note**  
To get the ARN of the domain, run the `describe-domain` command:
- **Note**  
To get the ARN of the domain, run the `describe-domain` command:
- **Note**  
To get the ARN of the domain, run the `describe-domain` command:
- **Note**  
If you delete a domain, all tag associations are removed from the deleted domain\. You do not have to remove tags before you delete a domain\.
- **Note**  
To get the ARN of the domain, run the `describe-domain` command:

