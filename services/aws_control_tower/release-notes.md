---
id: Release notes
title: Release notes
created: 1683841041000
updated: 1683841041000
---
# Release notes

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## January - December 2022

- **Important**  
When you initially set the value of `enable_stack_set_deletion` to `true`, the next time you invoke CfCT, **ALL** resources that begin with the prefix `CustomControlTower-`, which have the associated key tag `Key:AWS_Solutions, Value: CustomControlTowerStackSet`, and which are not declared in the manifest file, are staged for deletion\.
- **Note**  
After you update to version 3\.0 or later, you do not have the option to continue with account\-level CloudTrail trails managed by AWS Control Tower\.
- **Tip**  
If you plan to create and manage your own account\-level trails, we recommend that you create the new trails before you complete the update to AWS Control Tower landing zone version 3\.0, to start logging right away\.
- **Note**  
For landing zones at version 3\.0 or later, account\-level AWS CloudTrail trails are not supported by AWS Control Tower\. You can create and maintain your own account\-level trails at any time, or you can opt into organization\-level trails managed by AWS Control Tower\.


## January - December 2020

- **Note**  
Updating your landing zone does not automatically update your accounts\. If you have more than a few accounts, the required updates can be time\-consuming\. For that reason, we recommend that you avoid expanding your AWS Control Tower landing zone into Regions in which you do not require your workloads to run\.
- **Note**  
In April 2020, the **Quick account provisioning** capability was renamed to **Enroll account**\. In June 2022, the ability to create and update accounts in the AWS Control Tower console was separated from the ability to enroll AWS accounts\. For more information, see [Enroll an existing account](quick-account-provisioning.md)\.

