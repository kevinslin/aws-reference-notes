---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## Quick start guide

- **Note**  
AWS Control Tower sets up paid services, such as AWS CloudTrail, AWS Config, Amazon CloudWatch, Amazon S3, and Amazon VPC\. When used, these services may incur costs, as shown on the [pricing page](http://aws.amazon.com/controltower/pricing/?loc=ft)\. The AWS management console shows you the usage of any paid services and the costs incurred\. No additional costs are created by AWS Control Tower itself\.
- **Note**  
By default, AWS Control Tower chooses the Region in which your account is operating currently as your home Region\. You can see your current Region in the upper right of your AWS management console screen\.
- **Note**  
If you are a first\-time customer and you encounter a setup issue, contact [AWS Support](https://aws.amazon.com/premiumsupport/) for diagnostic assistance\.


## Pre-launch checks

- **Note**  
When launching, AWS Security Token Service \(STS\) endpoints must be activated in the management account, for all Regions governed by AWS Control Tower\. Otherwise, the launch may fail midway through the configuration process\.


## Step 1: Create your shared account email addresses

- **Note**  
If you specify existing AWS accounts as your **audit** and **log archive** accounts, the existing accounts must pass some pre\-launch checks to ensure that no resources are in conflict with AWS Control Tower requirements\. If these checks are not successful, your landing zone setup may not succeed\. In particular, the accounts must not have existing AWS Config resources\. For more information, see [Considerations for bringing existing security or logging accounts](accounts.md#considerations-for-existing-shared-accounts)\.
- **Note**  
We are changing our terminology regarding the default names of some AWS Control Tower organizational units \(OUs\) to align with the AWS multi\-account strategy\. You may notice some inconsistencies while we are making a transition to improve the clarity of these names\. The Security OU was formerly called the Core OU\. The Sandbox OU was formerly called the Custom OU\.


## Step 2. Configure and launch your landing zone

- **Important**  
Changing your home Region after you have deployed your AWS Control Tower landing zone requires decommissioning as well as the assistance of AWS Support\. This practice is not recommended\.


## Next steps

- **Important**  
If you have not yet enabled MFA for your account's root user, do so now\. For more information about best practices for the root user, see [Best practices to protect your account's root user](https://docs.aws.amazon.com/accounts/latest/reference/best-practices-root-user.html#bp-root-limit-tasks)\.

