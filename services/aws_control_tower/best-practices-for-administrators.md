---
id: Best practices for administrators
title: Best practices for administrators
created: 1683841041000
updated: 1683841041000
---
# Best practices for administrators

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## Plan your landing zone

- **Note**  
You can have one landing zone per organization\.
- **Note**  
If you already have an AWS Organizations landing zone, you can extend AWS Control Tower governance from the existing landing zone to some or all of your existing OUs and accounts within an organization\. See [Govern existing organizations and accounts](https://docs.aws.amazon.com/controltower/latest/userguide/importing-existing.html)\.
- **Important**  
Special consideration: If you currently are using the [AWS Landing Zone solution \(ALZ\)](http://aws.amazon.com/solutions/implementations/aws-landing-zone/) for AWS Organizations, check with your AWS solutions architect before you try to enable AWS Control Tower in your organization\. AWS Control Tower cannot perform pre\-checks that determine whether AWS Control Tower may interfere with your current landing zone deployment\. For more information, see [Walkthrough: Move from ALZ to AWS Control Tower](alz-to-control-tower.md)\. Also, for information about moving accounts from one landing zone to another, see [What if the account does not meet the prerequisites?](enroll-account.md#fulfill-prerequisites)
- **Note**  
To set up AWS Control Tower on an existing organization, your service limits must allow for the creation of at least two additional accounts\.
- **Important**  
Launching your AWS Control Tower landing zone in an existing AWS Organizations organization does not enable you to extend AWS Control Tower governance from that organization to other OUs or accounts that are not registered with AWS Control Tower\.


## Best practices: Set up an AWS multi-account landing zone

- **Note**  
An AWS account is not the same as a user account, which is set up through Federation or AWS Identity and Access Management \(IAM\)\.
- **Note**  
The names given in the examples follow the suggested AWS naming conventions for setting up a multi\-account AWS environment\. You can rename your OUs after you've set up your landing zone, by selecting **Edit** on the OU detail page\.


## Account Factory guidance

- **Note**  
 Up to five accounts can be provisioned at a time\.


## Configuration update management

- **Note**  
 The AWS Control Tower console indicates when your landing zone needs to be updated\. If you don't see an option to update, your landing zone is already up to date\.

