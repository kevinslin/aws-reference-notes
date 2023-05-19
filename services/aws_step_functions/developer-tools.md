---
id: Developer tools
title: Developer tools
created: 1683841041000
updated: 1683841041000
---
# Developer tools

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## Development Options

- **Note**  
Step Functions only supports  HTTPS endpoints\.
- **Note**  
YAML allows single line comments\. Any YAML comments provided in the state machine definition portion of a template will not be carried forward into the created resource’s definition\. Instead, you can use the `Comment` property within the state machine definition\. For more information, see the [State Machine Structure](amazon-states-language-state-machine-structure.md) page\.
- **Note**  
AWS CloudFormation and AWS SAM also allow you to upload your state machine definitions to Amazon S3 in JSON or YAML format, and to provide the definition's Amazon S3 location in the template\. This can improve the readability of your templates when your state machine definition is complex\. For more information see the [AWS::StepFunctions::StateMachine S3Location](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-stepfunctions-statemachine-s3location.html) page\.


## Step Functions and AWS SAM

- **Note**  
When using AWS SAM local, you can emulate Lambda and API Gateway locally\. However, you can't emulate Step Functions locally using AWS SAM\.


## Creating a Lambda State Machine Using AWS CloudFormation

- **Important**  
Ensure that your Lambda function is under the same AWS account and AWS Region as your state machine\.


## Creating a Lambda State Machine Using the AWS CDK

- **Note**  
Be sure to name the directory `step`\. The AWS CDK application template uses the name of the directory to generate names for source files and classes\. If you use a different name, your app will not match this tutorial\.


## Creating an API Gateway REST API with Synchronous Express State Machine Using the AWS CDK

- **Note**  
Be sure to name the directory `stepfunctions-rest-api`\. The AWS CDK application template uses the name of the directory to generate names for source files and classes\. If you use a different name, your app will not match this tutorial\.
- **Note**  
The State Machine that we will show here will be a simple State Machine with a `Pass` state\.
- **Note**  
For the purpose of this tutorial, we will test the `POST` HTTP method\.
- **Tip**  
Try the API Gateway with different Methods and an invalid input to see the error output\. You may want to change the state machine to look for a particular key and during testing provide the wrong key to fail the State Machine execution and generate an error message in the **Response Body** output\.
- **Tip**  
Try the API Gateway with different Methods and an invalid input to see the error output\. You may want to change the state machine to look for a particular key and during testing provide the wrong key to fail the State Machine execution and generate an error message in the **Response Body** output\.

