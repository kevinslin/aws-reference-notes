---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## Create a Step Functions state machine that uses Lambda

- **Note**  
In Step Functions, a workflow is called a *state machine*, which is a series of event\-driven steps\. Each step in a workflow is called a *state*\. A `Task` state represents a unit of work that another AWS service, such as AWS Lambda, performs\. A `Task` state can call any AWS service or API\. For more information, see:  
[What is AWS Step Functions?](welcome.md)
[Call other AWS services](connect-to-services.md)
- **Important**  
Ensure that your Lambda function is under the same AWS account and AWS Region as your state machine\.
- **Note**  
You can also pass payloads while invoking Lambda from a state machine\. For more information and examples about invoking Lambda by passing payload in the `Parameters` field, see [Invoke Lambda with Step Functions](connect-lambda.md)\.


## Handling Error Conditions Using a State Machine

- **Note**  
You can also create state machines that `Retry` on timeouts or those that use `Catch` to transition to a specific state when an error or timeout occurs\. For examples of these error handling techniques, see [Examples Using Retry and Using Catch](concepts-error-handling.md#error-handling-examples)\.
- **Important**  
Ensure that your Lambda function is under the same AWS account and AWS Region as your state machine\.


## Starting a State Machine Execution in Response to Amazon S3 Events

- **Note**  
You must configure EventBridge rule in the same AWS Region as the Amazon S3 bucket\.


## Creating a Step Functions API Using API Gateway

- **Note**  
Although Amazon API Gateway can start a Step Functions execution by calling `[StartExecution](https://docs.aws.amazon.com/step-functions/latest/apireference/API_StartExecution.html)`, you must call `[DescribeExecution](https://docs.aws.amazon.com/step-functions/latest/apireference/API_DescribeExecution.html)` to get the result\.
- **Note**  
For more information, see the `StartExecution` [Request Syntax](https://docs.aws.amazon.com/step-functions/latest/apireference/API_StartExecution.html#API_StartExecution_RequestSyntax) in the *AWS Step Functions API Reference*\.  
If you don't want to include the ARN of your state machine in the body of your API Gateway call, you can configure a body\-mapping template, as shown in the following example\.
- **Note**  
You can view the execution by choosing your state machine on the [AWS Step Functions console](https://console.aws.amazon.com/states/)\.


## Creating an Activity State Machine

- **Important**  
Ensure that your activity task is under the same AWS account as your state machine\.
- **Note**  
For a more complete example of an activity worker, see [Example Activity Worker in Ruby](example-ruby-activity-worker.md)\. This example provides an implementation based on best practices, which you can use as a reference for your activity worker\. The code implements a consumer\-producer pattern with a configurable number of threads for pollers and activity workers\.
- **Note**  
The `EnvironmentVariableCredentialsProvider` class in this example assumes that the `AWS_ACCESS_KEY_ID` \(or `AWS_ACCESS_KEY`\) and `AWS_SECRET_KEY` \(or `AWS_SECRET_ACCESS_KEY`\) environment variables are set\. For more information about providing the required credentials to the factory, see [AWSCredentialsProvider](https://docs.aws.amazon.com/AWSJavaSDK/latest/javadoc/com/amazonaws/auth/AWSCredentialsProvider.html) in the *AWS SDK for Java API Reference* and [Set Up AWS Credentials and Region for Development](https://docs.aws.amazon.com/sdk-for-java/v1/developer-guide/setup-credentials.html) in the *AWS SDK for Java Developer Guide*\.  
By default the AWS SDK will wait up to 50 seconds to receive data from the server for any operation\. The `GetActivityTask` operation is a long\-poll operation that will wait up to 60 seconds for the next available task\. To prevent receiving a `SocketTimeoutException` error, set SocketTimeout to 70 seconds\.


## Iterating a Loop Using Lambda

- **Note**  
If you set `index` to `9` for this test, the `index` increments to `10`, and `continue` is `false`\.


## Continuing Ongoing Work as a New Execution

- **Note**  
If you have completed the [Iterating a Loop Using Lambda](tutorial-create-iterate-pattern-section.md) tutorial, you can skip this step and use that Lambda function\.
- **Note**  
If you set `index` to `9` for this test, the `index` increments to `10`, and `continue` is `false`\.
- **Note**  
Save the Amazon Resource Name \(ARN\) of this state machine\.
- **Note**  
You can update the `"Resource": "*"` line in the previous example to reference the ARN of your `ContinueAsNew` state machine\. This restricts the policy so that it can only start an execution of that specific state machine\.


## Using Code Snippets

- **Note**  
Under the **Task state options** section, you can also configure `Retry`, `Catch`, and `TimeoutSeconds` options\. See [Error handling in Step Functions](concepts-error-handling.md)\.


## Deploying an Example Human Approval Project

- **Note**  
You will need to provide a valid email address that you have access to when you create the AWS CloudFormation stack\.


## View X-Ray traces in Step Functions

- **Important**  
Ensure that your Lambda function is under the same AWS account and AWS Region as your state machine\.

