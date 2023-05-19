---
id: Multi-account permissions
title: Multi-account permissions
created: 1683841041000
updated: 1683841041000
---
# Multi-account permissions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-single-sign-on-user-guide.git)
{% endhint %}

## Delegated administration

- **Note**  
If your IAM Identity Center configuration was enabled prior to November 2019 and you have not yet enabled access to other accounts in AWS Organizations, you might see an info alert in the console to enable access to IAM Identity Center for a member account in your organization\. To provide a registered delegated administrator access to your users and groups and to setup entitlements you have to [Allow Identity Center enabled applications in AWS accounts](app-enablement.md#enable-app-enablement)\. If your IAM Identity Center configuration was enabled after November 2019, there is nothing more for you to do because access to accounts in your organization were automatically enabled by AWS\.
- **Important**  
This operation delegates IAM Identity Center administrative access to admin users in this member account\. All users who have sufficient permissions to this delegated administrator account can perform all IAM Identity Center administrative tasks from the account, except for: enabling IAM Identity Center, deleting IAM Identity Center configurations, managing permission sets provisioned in the management account, registering or deregistering other member accounts as delegated administrators, or enabling or disabling user access in the management account\.
- **Important**  
When you deregister an account, you effectively remove the ability for all admin users to manage IAM Identity Center from that account\. As a result, they can no longer administer IAM Identity Center identities, access management, authentication, or application access from this account\. This operation will not affect any permissions or assignments configured in IAM Identity Center and therefore will have no impact on your end users as they will continue to have access to their apps and AWS accounts from within the AWS access portal\.


## Single sign-on access to AWS accounts

- **Note**  
You might need to grant users or groups permissions to operate in the AWS Organizations management account\. Because it is a highly privileged account, additional security restrictions require you to have the [IAMFullAccess](https://console.aws.amazon.com/iam/home#policies/arn:aws:iam::aws:policy/IAMFullAccess) policy or equivalent permissions before you can set this up\. These additional security restrictions are not required for any of the member accounts in your AWS organization\.
- **Note**  
To simplify administration of access permissions, we recommended that you assign access directly to groups rather than to individual users\. With groups you can grant or deny permissions to groups of users rather than having to apply those permissions to each individual\. If a user moves to a different organization, you simply move that user to a different group and they automatically receive the permissions that are needed for the new organization\.

