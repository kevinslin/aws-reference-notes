---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-chatbot-admin-guide.git)
{% endhint %}

## Tutorial: Get started (Slack)

- **Note**  
You can configure a Slack channel to run commands to your AWS account\. For more information, see [Running AWS CLI commands from chat channels](chatbot-cli-commands.md)\.


## Tutorial: Get started (Teams)

- **Note**  
The following IAM permissions are required to create a Microsoft Teams configuration:  
GetMicrosoftTeamsOauthParameters
RedeemMicrosoftTeamsOauthCode
CreateMicrosoftTeamsChannelConfiguration
If you have less that administrative permissions, ensure you have the aforementioned permissions to create a configuration\.
- **Note**  
You can configure a Microsoft Teams channel to run commands to your AWS account\. For more information, see [Running AWS CLI commands from chat channels](chatbot-cli-commands.md)\.


## Tutorial: Subscribing an Amazon SNS topic to AWS Chatbot

- **Note**  
You can set up each supported AWS service to *target* one or more SNS topics to send notifications to AWS Chatbot\. You do this using each AWS service's console, or using AWS CloudFormation\. If you already have Amazon SNS topics set as targets for supported services, you can configure AWS Chatbot to use those topics\. Notifications from subscribed topics will automatically appear in your chat channels without further configuration\.
- **Note**  
If your SNS topic is encrypted, you must add a section to your AWS KMS key policy to give the sending service permissions to post events to the encrypted SNS topics\. For more information, see [Setting up Amazon SNS topics](getting-started.md#chatbot-sns)\.


## Test notifications with AWS Chatbot using CloudWatch

- **Note**  
CloudWatch alarms and events are separately configured and have different characteristics for use with AWS Chatbot\.

