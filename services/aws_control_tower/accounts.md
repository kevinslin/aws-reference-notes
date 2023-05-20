---
id: Accounts
title: Accounts
created: 1683841041000
updated: 1683841041000
---
# Accounts

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## About accounts

- **Note**  
As a best practice, we recommend signing in as an IAM Identity Center user with **Administrator** privileges when performing administrative functions within the AWS Control Tower console, instead of the signing in as the root user or IAM administrator user for this account\.
- **Note**  
These logs cannot be changed\. All logs are stored for the purposes of audit and compliance investigations related to account activity\.
- **Important**  
The email address you provided for the audit account receives **AWS Notification \- Subscription Confirmation** emails from every AWS Region supported by AWS Control Tower\. To receive compliance emails in your audit account, you must choose the **Confirm subscription** link within each email from each AWS Region supported by AWS Control Tower\.


## Enroll an existing AWS account

- **Note**  
You cannot enroll an existing account to serve as your audit or log archive account except during initial landing zone setup\.
- **Note**  
When you enroll the account into AWS Control Tower, your account is governed by the AWS CloudTrail trail for the new organization\. If you have an existing deployment of a CloudTrail trail, you may see duplicate charges unless you delete the existing trail for the account before you enroll it in AWS Control Tower\.
- **Tip**  
You can change the default behavior for new accounts by configuring Account Factory, so it does not set up a VPC by default for accounts in your organization under AWS Control Tower\. For more information, see [Create an Account in AWS Control Tower Without a VPC](configure-without-vpc.md#create-without-vpc)\.
- **Tip**  
 You can send the invitation for the new organization before the account drops out of the old organization\. The invitation will be waiting when the account officially drops out of its existing organization\.


## Enroll accounts that have existing AWS Config resources

- **Note**  
If you plan to bring existing AWS accounts into AWS Control Tower as **Audit** and **Log archive** accounts, and if those accounts have existing AWS Config resources, you must delete the existing AWS Config resources before you can enroll the accounts into AWS Control Tower\.
- **Note**  
Any SCPs that you create should exclude an `aws-controltower-ConfigRecorderRole*` role\. Do not modify the permissions that restrict the ability for AWS Config rules to perform evaluations\.  
Follow these guidelines so that you don't receive an `AccessDeniedException` when you have SCPs that block `aws-controltower-ConfigRecorderRole*` from calling Config\.
- **Note**  
The **Enroll account** workflow will not succeed for this task\. You must choose **Register OU** or **Re\-register OU**\.


## Account Factory

- **Note**  
Exercise caution when working from the management account, as you would when using any account that has permissions across your organization\.
- **Note**  
To enroll an existing AWS account into AWS Control Tower, that account must have the `AWSControlTowerExecution` role enabled\. For more information about how to enroll an existing account, see [Enroll an existing AWS account](enroll-account.md)\.
- **Note**  
 When updating a provisioned product that's associated with an account that Account Factory vends, if you specify a new user email address for AWS IAM Identity Center \(successor to AWS Single Sign\-On\), AWS Control Tower creates a new user in IAM Identity Center\. The previously created account isn't removed\. For information about removing the previous IAM Identity Center user email address from IAM Identity Center, see [Disabling a User](https://docs.aws.amazon.com/singlesignon/latest/userguide/disableuser.html)\.


## Account Factory Customization (AFC)

- **Note**  
AWS Control Tower contains *proactive controls*, which monitor AWS CloudFormation resources in AWS Control Tower\. Optionally, you can activate these controls in your landing zone\. When you apply proactive controls, they check to make sure that the resources you're about to deploy to your accounts are compliant with your organization's policies and procedures\. For more information about proactive controls, see [Proactive controls](proactive-controls.md)\.
- **Note**  
One blueprint may be deployed per AWS Control Tower account\.


## AWS Control Tower Account Factory for Terraform (AFT)

- **Note**  
 AFT doesn't impact workflow performance in AWS Control Tower\. If you provision an account through AFT or Account Factory, the same backend workflow occurs\.
- **Tip**  
 Optionally, you can create an account template folder in the **aft\-account\-customizations** repository\.

