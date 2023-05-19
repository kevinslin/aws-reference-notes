---
id: Setting up
title: Setting up
created: 1683841041000
updated: 1683841041000
---
# Setting up

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## Individual user setup

- **Important**  
Although you can sign in to the AWS Cloud9 console with the email address and password that you used when you created your AWS account \(we call this an AWS account *root user*\), this isn't an AWS security best practice\. In the future, we recommend that you sign in as an administrator user in AWS Identity and Access Management \(IAM\) in your AWS account instead\. For more information, see [Creating Your First IAM Admin User and Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html) in the *IAM User Guide* and [AWS Tasks That Require AWS Account Root User Credentials](https://docs.aws.amazon.com/general/latest/gr/aws_tasks-that-require-root.html) in the *Amazon Web Services General Reference*\.


## Team setup

- **Note**  
You can use [IAM Identity Center](https://aws.amazon.com/single-sign-on/) instead of IAM to enable multiple users within a single AWS account to use AWS Cloud9\. In this usage pattern, the single AWS account serves as the management account for an organization in AWS Organizations, and that organization has no member accounts\. To use IAM Identity Center, skip this topic and follow the instructions in [Enterprise Setup](setup-enterprise.md) instead\. For related information, see the following resources:  
 [What is AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_introduction.html) in the *AWS Organizations User Guide* \(IAM Identity Center requires the use of AWS Organizations\)
 [What is AWS IAM Identity Center \(successor to AWS Single Sign\-On\)](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html) in the *AWS IAM Identity Center \(successor to AWS Single Sign\-On\) User Guide* 
The 4\-minute video [AWS Knowledge Center Videos: How do I get started with AWS Organizations](https://www.youtube.com/watch?v=8VKMrkKXu2w) on the YouTube website
The 7\-minute video [Manage user access to multiple AWS accounts using IAM Identity Center](https://www.youtube.com/watch?v=bXrsUEI1V38) on the YouTube website
The 9\-minute video [How to set up IAM Identity Center for your on\-premise Active Directory users](https://www.youtube.com/watch?v=nuPjljOVZmU) on the YouTube website
- **Note**  
Your organization might already have an AWS account set up for you\. If your organization has an AWS account administrator, check with that person before starting the following procedure\. If you already have an AWS account, skip ahead to [Step 2: Create an IAM Group and User, and Add the User to the Group](#setup-create-iam-resources)\.
- **Note**  
Your organization might already have an IAM group and user set up for you\. If your organization has an AWS account administrator, check with that person before starting the following procedures\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
We recommend that you repeat this procedure to create at least two groups: one group for AWS Cloud9 users, and another group for AWS Cloud9 administrators\. This AWS security best practice can help you better control, track, and troubleshoot issues with AWS resource access\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
Your organization might already have a group set up for you with the appropriate access permissions\. If your organization has an AWS account administrator, check with that person before starting the following procedure\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
If you have more than one group you want to add AWS Cloud9 access permissions to, repeat this procedure for each of those groups\.


## Enterprise setup

- **Note**  
Your enterprise might already have a management account set up for you\. If your enterprise has an AWS account administrator, check with that person before starting the following procedure\. If you already have a management account, skip ahead to [Step 2: Create an Organization for the management account](#setup-enterprise-create-organization)\.
- **Note**  
Your enterprise might already have AWS Organizations set up to use the management account\. If your enterprise has an AWS account administrator, check with that person before starting the following procedure\. If you already have AWS Organizations set up to use the management account, skip ahead to [Step 3: Add member accounts to the organization](#setup-enterprise-add-to-organization)\.
- **Note**  
Your enterprise might already have AWS Organizations set up with the wanted member accounts\. If your enterprise has an AWS account administrator, check with that person before starting the following procedure\. If you already have AWS Organizations set up with the wanted member accounts, skip ahead to [Step 4: Enable IAM Identity Center across the organization](#setup-enterprise-set-up-sso)\.
- **Note**  
You don't have to add any member accounts to the organization\. You can use IAM Identity Center with just the single management account in the organization\. Later, you can add member accounts to the organization, if you want\. If you don't want to add any member accounts now, skip ahead to [Step 4: Enable IAM Identity Center across the organization](#setup-enterprise-set-up-sso)\.
- **Note**  
Your enterprise might already have AWS Organizations set up to use IAM Identity Center\. If your enterprise has an AWS account administrator, check with that person before starting the following procedure\. If you already have AWS Organizations set up to use IAM Identity Center, skip ahead to [Step 5\. Set up groups and users within the organization](#setup-enterprise-set-up-groups-users)\.
- **Note**  
Your enterprise might already have AWS Organizations set up with groups and users from either an IAM Identity Center directory or an AWS Managed Microsoft AD or AD Connector directory that is managed in AWS Directory Service\. If your enterprise has an AWS account administrator, check with that person before starting the following procedure\. If you already have AWS Organizations set up with groups and users from either an IAM Identity Center directory or AWS Directory Service, skip ahead to [Step 6\. Enable groups and users within the organization to use AWS Cloud9](#setup-enterprise-groups-users-access)\.


## Additional setup options (team and enterprise)

- **Note**  
The following procedures cover attaching and detaching policies for AWS Cloud9 users only\. These procedures assume you already have a separate AWS Cloud9 users group and AWS Cloud9 administrators group and that you have only a limited number of users in the AWS Cloud9 administrators group\. This AWS security best practice can help you better control, track, and troubleshoot issues with AWS resource access\.
- **Note**  
This step covers creating a customer managed policy for IAM groups only\. To create a custom permission set for groups in AWS IAM Identity Center \(successor to AWS Single Sign\-On\), skip this step and follow the instructions in [Create Permission Set](https://docs.aws.amazon.com/singlesignon/latest/userguide/permissionsets.html#howtocreatepermissionset) in the *AWS IAM Identity Center \(successor to AWS Single Sign\-On\) User Guide* instead\. In this topic, follow the instructions to create a custom permission set\. For related custom permissions policies, see [Customer managed policy examples for teams using AWS Cloud9](#setup-teams-policy-examples) later in this topic\.
- **Note**  
This step covers adding customer managed policies to IAM groups only\. To add custom permission sets to groups in AWS IAM Identity Center \(successor to AWS Single Sign\-On\), skip this step and follow the instructions in [Assign User Access](https://docs.aws.amazon.com/singlesignon/latest/userguide/useraccess.html#assignusers) in the *AWS IAM Identity Center \(successor to AWS Single Sign\-On\) User Guide* instead\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
AWS Cloud9 doesn't enable restricting the creation of environments to specific AWS Regions\. Nor does it enable restricting the overall number of environments that can be created \(other than the published [service limits](limits.md)\)\.

