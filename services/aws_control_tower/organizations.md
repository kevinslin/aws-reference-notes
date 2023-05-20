---
id: Organizations
title: Organizations
created: 1683841041000
updated: 1683841041000
---
# Organizations

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## Extend governance to an existing organization

- **Note**  
During set up, AWS Control Tower performs pre\-checks to avoid common issues\. However, if you are currently using the AWS Landing Zone solution for AWS Organizations, check with your AWS solutions architect before you try to enable AWS Control Tower in your organization to determine if AWS Control Tower may interfere with your current landing zone deployment\. Also, see [What if the account does not meet the prerequisites?](enroll-account.md#fulfill-prerequisites) for information about moving accounts from one landing zone to another\.


## Nested OUs

- **Tip**  
You can make use of control inheritance to help stay within an OU's SCP quota\. For example, you can enable a control at the top\-level OU of an OU hierarchy, instead of enabling directly for a nested OU\.
- **Note**  
The status **Inherited** indicates that the control was applied to an OU higher in the tree, and it is enforced on this OU, but it was not added directly to this OU\.


## Register an OU to enroll multiple accounts

- **Note**  
If you don't already have an AWS Control Tower landing zone, start by setting up a landing zone, either in a new organization created by AWS Control Tower, or in an existing AWS Organizations organization\. For more details about how to set up a landing zone, see [Getting started with AWS Control Tower](getting-started-with-control-tower.md)\.


## Update organizations

- **Tip**  
When you re\-register an OU, or when you're updating your landing zone version and multiple member accounts, you may see a failure message mentioning the **StackSet\-AWSControlTowerExecutionRole**\. This StackSet in the management account can fail because the **AWSControlTowerExecution** IAM role already exists in all enrolled member accounts\. This error message is expected behavior, and it can be disregarded\.

