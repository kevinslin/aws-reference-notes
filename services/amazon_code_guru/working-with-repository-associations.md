---
id: Working with repository associations
title: Working with repository associations
created: 1683841041000
updated: 1683841041000
---
# Working with repository associations

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-codeguru-reviewer-user-guide.git)
{% endhint %}

## Create a GitHub or GitHub Enterprise Cloud repository association

- **Note**  
We recommend creating a new GitHub user \(for example, *MyCodeGuruUser*\) and using that user to provide CodeGuru Reviewer with access to your GitHub repositories\. This ensures that CodeGuru Reviewer posts comments on behalf of a unique user\. This helps avoid confusion and make the account more transferable, so that it doesn't belong to a single person who might not always be available to maintain it\.


## Create a GitHub Enterprise Server repository association

- **Note**  
GitHub Enterprise Cloud repositories have a different procedure and different prerequisites\. If you're using GitHub Enterprise Cloud, [follow this procedure instead](https://docs.aws.amazon.com/codeguru/latest/reviewer-ug/create-github-association.html)\.
- **Important**  
AWS CodeStar connections does not support GitHub Enterprise Server version 2\.22\.0 due to a known issue in the release\. To create a connection, use version 2\.22\.1 or later\.


## Disassociate a repository

- **Note**  
Charges are not incurred for disassociated repositories\.


## Encrypting a repository association

- **Note**  
Creation of an AWS KMS key results in charges to your AWS account\. For more information, see [AWS Key Management Service pricing](http://aws.amazon.com/kms/pricing)\.

