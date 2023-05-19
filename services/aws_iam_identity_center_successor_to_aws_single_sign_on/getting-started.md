---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-single-sign-on-user-guide.git)
{% endhint %}

## Step 1: Enable IAM Identity Center

- **Note**  
If you are using a multi\-account environment, we recommend that you configure delegated administration\. With delegated administration, you can limit the number of people who require access to the management account in AWS Organizations\. For more information, see [Delegated administration](delegated-admin.md)\.


## Step 2: Choose your identity source

- **Important**  
If you're already managing users and groups in Active Directory or an external identity provider \(IdP\), we recommend that you consider connecting this identity source when you enable IAM Identity Center and choose your identity source\. This should be done before you create any users and groups in the default Identity Center directory and make any assignments\. If you're already managing users and groups in one identity source in IAM Identity Center, changing to a different identity source might remove all user and group assignments that you configured in IAM Identity Center\. If this occurs, all users, including the administrative user in IAM Identity Center, will lose single sign\-on access to their AWS accounts and applications\. For more information, see [Considerations for changing your identity source](manage-your-identity-source-considerations.md)\.

