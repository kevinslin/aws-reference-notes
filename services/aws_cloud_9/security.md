---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## Identity and access management

- **Important**  
As an AWS security best practice, we recommend that you use the root credentials only to create an IAM *administrator group* with an IAM *administrator user*\. This is a group that gives the user full permissions to your AWS account\. Then you can use this administrator user to create other IAM users and roles with limited permissions\. For more information, see [Create Individual IAM Users](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#create-iam-users) and [Creating Your First IAM Admin User and Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html) in the *IAM User Guide*\.
- **Note**  
Instead of attaching an instance profile to an Amazon EC2 instance that connects to an environment, AWS Cloud9 can automatically set up and manage temporary credentials on your behalf in an EC2 environment\. For more information, see [AWS managed temporary credentials](#auth-and-access-control-temporary-managed-credentials)\.
- **Note**  
This section discusses the use of IAM in AWS Cloud9\. It doesn't provide detailed information about the IAM service\. For complete IAM documentation, see [What Is IAM?](https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html) in the *IAM User Guide*\. For information about IAM policy syntax and descriptions, see the [IAM JSON Policy Reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html) in the *IAM User Guide*\.
- **Note**  
The following examples use the US East \(Ohio\) Region \(`us-east-2`\), a fictitious AWS account ID \(`123456789012`\), and a fictitious AWS Cloud9 development environment ID \(`81e900317347585a0601e04c8d52eaEX`\)\.
- **Note**  
The preceding access permission is already included in the AWS managed policies `AWSCloud9Administrator` and `AWSCloud9User`\.
- **Note**  
The preceding access permission is already included in the AWS managed policies `AWSCloud9Administrator` and `AWSCloud9User`\.
- **Note**  
If the AWS managed policy `AWSCloud9Administrator` or `AWSCloud9User` is already attached to the IAM entity, that AWS managed policy overrides the behavior of the preceding IAM policy statement\. This is because those AWS managed policies are more permissive\.
- **Note**  
If the AWS managed policy `AWSCloud9Administrator` or `AWSCloud9User` is already attached to the IAM entity, that AWS managed policy overrides the behavior of the preceding IAM policy statement\. This is because those AWS managed policies are more permissive\.
- **Note**  
If the AWS managed policy `AWSCloud9Administrator` or `AWSCloud9User` is already attached to the IAM entity, that AWS managed policy overrides the behavior of the preceding IAM policy statement\. This is because those AWS managed policies are more permissive\.
- **Note**  
The preceding access permission is already included in the AWS managed policy `AWSCloud9Administrator`\.
- **Note**  
The preceding access permission is already included in the AWS managed policy `AWSCloud9Administrator`\. Also, the preceding access permission is more permissive than the equivalent access permission in the AWS managed policy `AWSCloud9User`\.
- **Note**  
If the AWS managed policy `AWSCloud9Administrator` or `AWSCloud9User` is already attached to the IAM entity, those AWS managed policies overrides the behavior of the preceding IAM policy statement\. This is because those AWS managed policies are more permissive\.
- **Note**  
The preceding access permission is already included in the AWS managed policy `AWSCloud9Administrator`\.
- **Note**  
The preceding access permission is already included in the AWS managed policy `AWSCloud9Administrator`\.
- **Note**  
The preceding access permission is already included in the AWS managed policy `AWSCloud9Administrator`\.
- **Note**  
The preceding access permission is already included in the AWS managed policy `AWSCloud9Administrator`\. Also, that the preceding access permission is more permissive than the equivalent access permission in the AWS managed policy `AWSCloud9User`\.
- **Note**  
You can use the tables below as a reference when you're setting up access control and writing permissions policies to attach to an IAM identity \(identity\-based policies\)\.   
The [Public API operations](#callable-api) table lists API operations that can be called by customers using SDKs and the AWS Command Line Interface\.  
 The [Permission-only API operations](#permissions-only-api) lists API operations that are not directly callable by customer code or the AWS Command Line Interface\. But IAM users do require permissions for these operations that are called when AWS Cloud9 actions are performed using the console\.
- **Important**  
Currently, if your environment’s EC2 instance is launched into a **private subnet**, you can't use AWS managed temporary credentials to allow the EC2 environment to access an AWS service on behalf of an AWS entity \(an IAM user, for example\)\.  
For more information about when you can launch an EC2 instance into a private subnet, see [Create a subnet for AWS Cloud9](vpc-settings.md#vpc-settings-create-subnet)\.
- **Note**  
It is recommended to use a AWS managed policy instead of an inline policy when you are using AWS managed temporary credentials\.
- **Note**  
You can also turn on or off AWS managed temporary credentials by calling the AWS Cloud9 API operation [https://docs.aws.amazon.com/cloud9/latest/APIReference/API_UpdateEnvironment.html](https://docs.aws.amazon.com/cloud9/latest/APIReference/API_UpdateEnvironment.html) and assigning a value to the `managedCredentialsAction` parameter\. You can request this API operation using standard AWS tools such as AWS SDKs and the AWS CLI\.
- **Important**  
AWS managed temporary credentials also expire automatically every 15 minutes\. For the credentials to be refreshed so that collaborators can continue to use them, the environment owner must be connected to AWS Cloud9 environment through the IDE\.


## Infrastructure security

- **Note**  
By default, AWS Cloud9 EC2 development environments automatically install security patches for the instances' system packages\.


## Configuration and vulnerability analysis

- **Important**  
If your environment's Amazon EC2 instance is based on an Amazon Linux 2 AMI or an Amazon Linux AMI template, security updates are installed on the instance immediately after it's launched\. And security patches are then automatically applied to the instance every hour\. These updates are applied by a background process and don't affect your use of the instance\.  
For an Ubuntu EC2 environment, security updates are also installed on the instance immediately after it's launched\. Then the `unattended-upgrades` package automatically installs available updates daily\.

