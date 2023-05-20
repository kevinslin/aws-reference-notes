---
id: Working with Your AWS CodeStar User Profile
title: Working with Your AWS CodeStar User Profile
created: 1683841041000
updated: 1683841041000
---
# Working with Your AWS CodeStar User Profile

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codestar-user-guide.git)
{% endhint %}

## Manage Display Information

- **Note**  
The information in this topic covers only your AWS CodeStar user profile\. If your project uses resources outside of AWS \(for example, a GitHub repository or issues in Atlassian JIRA\), those resource providers might use their own user profiles, which might have different settings\. For more information, see the resource provider's documentation\.
- **Important**  
To use the console to change the display information for a user, you must be signed in as that IAM user\. No other user, even those with the AWS CodeStar owner role for a project or with the `AWSCodeStarFullAccess` policy applied, can change your display information\.


## Add a Public Key to Your User Profile

- **Important**  
An AWS CodeStar project owner can grant project owners, contributors, and viewers SSH access to Amazon EC2 instances for the project, but only the individual \(owner, contributor, or viewer\) can set the SSH key\. To do this, the user must be signed in as the individual owner, contributor, or viewer\.   
AWS CodeStar does not manage SSH keys for AWS Cloud9 environments\.

