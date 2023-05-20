---
id: Working with Teams
title: Working with Teams
created: 1683841041000
updated: 1683841041000
---
# Working with Teams

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codestar-user-guide.git)
{% endhint %}

## Add Team Members to a Project

- **Important**  
Adding a team member does not affect that member's access to resources that are outside of AWS \(for example, a GitHub repository or issues in Atlassian JIRA\)\. Those access permissions are controlled by the resource provider, not AWS CodeStar\. For more information, see the resource provider's documentation\.  
Anyone who has access to an AWS CodeStar project can  use the AWS CodeStar console to access resources that are outside of AWS but related to that project\.  
Adding a team member to a project does not automatically allow that member to participate in any related AWS Cloud9 development environments for the project\. To allow a team member to participate in a shared environment, see [Share an AWS Cloud9 Environment with a Project Team Member](setting-up-ide-cloud9.md#setting-up-ide-cloud9-share)\.  
Granting federated user access to a project involves manually attaching the AWS CodeStar owner, contributor, or viewer managed policy to the role assumed by the federated user\. For more information, see [Federated User Access to AWS CodeStar](security_iam_service-with-iam.md#security_iam_service-with-iam-roles-federated)\.


## Manage Team Permissions

- **Important**  
To change a role for a team member, you must either have the AWS CodeStar owner role for that project or have the `AWSCodeStarFullAccess` policy applied\.  
Changing a team member's permissions does not affect that team member's access to any resources that are outside of AWS \(for example, a GitHub repository or issues in Atlassian JIRA\)\. Those access permissions are controlled by the resource provider, not AWS CodeStar\. For more information, see the resource provider's documentation\.  
Anyone who has access to an AWS CodeStar project may be able to use the AWS CodeStar console to access resources that are outside of AWS but are related to that project\.  
Changing a team member's role for a project does not automatically allow or prevent that member from participating in any AWS Cloud9 development environments for the project\. To allow or prevent a team member from participating in a shared environment, see [Share an AWS Cloud9 Environment with a Project Team Member](setting-up-ide-cloud9.md#setting-up-ide-cloud9-share)\.


## Remove Team Members from a Project

- **Important**  
Although removing a team member from a project denies remote access to project Amazon EC2 instances, it does not close any of the user's active SSH sessions\.  
Removing a team member does not affect that team member's access to any resources that are outside of AWS \(for example, a GitHub repository or issues in Atlassian JIRA\)\. Those access permissions are controlled by the resource provider, not AWS CodeStar\. For more information, see the resource provider's documentation\.  
Removing a team member from a project does not automatically delete that team member's related AWS Cloud9 development environments or prevent that member from participating in any related AWS Cloud9 development environments they have been invited to\. To delete a development environment, see [Delete an AWS Cloud9 Environment from a Project](setting-up-ide-cloud9.md#setting-up-ide-cloud9-delete)\. To prevent a team member from participating in a shared environment, see [Share an AWS Cloud9 Environment with a Project Team Member](setting-up-ide-cloud9.md#setting-up-ide-cloud9-share)\.

