---
id: What is IAM?
title: What is IAM?
created: 1683841041000
updated: 1683841041000
---
# What is IAM?

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/iam-user-guide.git)
{% endhint %}

## When do I use IAM

- **Note**  
If you are using IAM Identity Center to manage your users, you assign permission sets in IAM Identity Center instead of attaching a permissions policy to a principal\. When you assign a permission set to a group or user in AWS IAM Identity Center \(successor to AWS Single Sign\-On\), IAM Identity Center creates corresponding IAM roles in each account, and attaches the policies specified in the permission set to those roles\. IAM Identity Center manages the role, and allows the authorized users you’ve defined to assume the role\. If you modify the permission set, IAM Identity Center ensures that the corresponding IAM policies and roles are updated accordingly\.  
For more information about IAM Identity Center, see [What is IAM Identity Center?](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html) in the *AWS IAM Identity Center \(successor to AWS Single Sign\-On\) User Guide*\.


## Users in AWS

- **Note**  
For scenarios in which you need IAM users with programmatic access and long\-term credentials, we recommend that you rotate access keys\. For more information, see [Rotating access keys](id_credentials_access-keys.md#Using_RotateAccessKey)\.


## IAM console search

- **Note**  
Access key search requires you to type the full access key ID in the search box\. The search result shows the user associated with that key\. From there you can navigate directly to that user's page, where you can manage the access key\.

