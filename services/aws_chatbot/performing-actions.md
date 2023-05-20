---
id: Performing actions
title: Performing actions
created: 1683841041000
updated: 1683841041000
---
# Performing actions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-chatbot-admin-guide.git)
{% endhint %}

## Running AWS CLI commands from chat channels

- **Note**  
If you are using Slack and AWS is not listed as a valid member of the channel, you need to add the AWS Chatbot app to the Slack workspace and invite it to the channel\. For more information, see the [Getting started guide for AWS Chatbot](getting-started.md)\.
- **Note**  
You can specify parameters with either a double hyphen \(*\-\-option*\) or a single hyphen \(*\-option*\)\. This allows you to use a mobile device to run commands without running into issues with the mobile device automatically converting a double hyphen to a long dash\.
- **Note**  
AWS CLI commands run from AWS Chatbot have an execution [timeout](https://docs.aws.amazon.com/whitepapers/latest/serverless-architectures-lambda/timeout.html) of 15 seconds\. If a command response is not received within 15 seconds, you receive a timeout error message\. If you have longer running jobs, such as AWS Lambda functions, you should invoke them asynchronously from AWS Chatbot\. The maximum allowable Lambda function execution timeout is 900 seconds \(15 minutes\)\. For more information about asynchronous invocation, see [Asynchronous invocation](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html) in the *AWS Lambda Developer Guide*\.
- **Note**  
If you find you are unable to run commands, you may need to switch your user role or contact your administrator to find out what actions are permissible\.
- **Important**  
If you have a large number of chat channels and you want to have the same command permissions across multiple channels, you can apply the configured AWS Chatbot role to any of your other chat channels without further modification\. The IAM policies will be consistent across chat channels that support commands in your AWS Chatbot service\.


## Creating and using command aliases in chat channels

- **Note**  
When a channel member runs a command alias, the target is run with the configured member's permissions \(channel role, user role\) depending on the permissions schemas in place\. For more information about permissions, see [Understanding AWS Chatbot permissions](understanding-permissions.md)\.
- **Note**  
The command alias definition can contain additional parameters\. Also note that *alias\_name* has a 100 character limit and *mapped\_action* has a 5,000 character limit\.


## Tutorial: Using AWS Chatbot to run an AWS Lambda function remotely

- **Important**  
Replace *<your region>* with the same AWS Region you set while using the Lambda, CloudWatch, and AWS Chatbot consoles\. You only need to specify the AWS Region in the channel once when you type your first AWS CLI command in Slack\.
**Tip**  
AWS Chatbot also supports certain simplified AWS CLI syntaxes\. For example, the simplified version of the previous command is shown following:

