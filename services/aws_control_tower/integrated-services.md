---
id: Integrated services
title: Integrated services
created: 1683841041000
updated: 1683841041000
---
# Integrated services

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## CloudTrail

- **Note**  
In AWS Control Tower releases before landing zone version 3\.0, AWS Control Tower created a member account trail in each account\. When you update to release 3\.0, your CloudTrail trail becomes an organization trail\. For best practices when moving between trails, see [Best practices for changing trails](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html#creating-an-organizational-trail-best-practice) in the *CloudTrail User Guide*\.
- **Note**  
When you update to landing zone version 3\.0, AWS Control Tower deletes the account\-level trails of your enrolled accounts on your behalf\. Your existing, account\-level log files are preserved in their Amazon S3 bucket\.


## AWS Organizations

- **Note**  
You can add additional OUs in your landing zone through the AWS Control Tower console on the **Organizational units** page\.


## IAM Identity Center

- **Note**  
You can delegate administration of AWS IAM Identity Center \(successor to AWS Single Sign\-On\) in your organization to an account other than the management account\. For more information, see this blog post, entitled, [Getting started with AWS SSO delegated administration](http://aws.amazon.com/blogs/security/getting-started-with-aws-sso-delegated-administration/)


## Amazon SNS

- **Tip**  
One of the best ways to receive AWS Control Tower control compliance notifications \(in your audit account\) is to subscribe to `AggregateConfigurationNotifications`\. It is a service that helps you inspect compliance\. It gives you real data about AWS Config rules going out of compliance\. AWS Config automatically maintains the list of accounts in your OU\.  
You must subscribe manually, using email or any type of subscription that SNS allows\. The statement `arn:aws:sns:homeregion:account:aws-controltower-AggregateSecurityNotifications` leads to your audit account\.

