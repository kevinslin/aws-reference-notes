---
id: How Step Functions works
title: How Step Functions works
created: 1683841041000
updated: 1683841041000
---
# How Step Functions works

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## Standard vs. Express Workflows

- **Note**  
If you define your state machines outside the Step Functions' console, such as in an editor of your choice, you must save your state machine definitions with the extension *\.asl\.json*\.


## States

- **Note**  
If you define your state machines outside the Step Functions' console, such as in an editor of your choice, you must save your state machine definitions with the extension *\.asl\.json*\.


## State Machine Data

- **Note**  
Numbers in JSON text format conform to JavaScript semantics\. These numbers typically correspond to double\-precision [IEEE\-854](https://standards.ieee.org/findstds/standard/854-1987.html) values\.
The following is valid JSON text: standalone, quote\-delimited strings; objects; arrays; numbers; Boolean values; and `null`\.
The output of a state becomes the input into the next state\. However, you can restrict states to working on a subset of the input data by using [Input and Output Processing](concepts-input-output-filtering.md)\.


## Input and Output Processing

- **Tip**  
Use the [ data flow simulator in the Step Functions console](https://console.aws.amazon.com/states/home?region=us-east-1#/simulator) to test JSON path syntax, to better understand how data is manipulated within a state, and to see how data is passed between states\.


## Error handling

- **Note**  
Unhandled errors in Lambda are reported as `Lambda.Unknown` in the error output\. These include out\-of\-memory errors and function timeouts\. You can match on `Lambda.Unknown`, `States.ALL`, or `States.TaskFailed` to handle these errors\. When Lambda hits the maximum number of invocations, the error is `Lambda.TooManyRequestsException`\. For more information about Lambda function errors, see [Error handling and automatic retries](https://docs.aws.amazon.com/lambda/latest/dg/invocation-retries.html) in the *AWS Lambda Developer Guide*\.
- **Note**  
Retries are treated as state transitions\. For information about how state transitions affect billing, see [Step Functions Pricing](https://aws.amazon.com/step-functions/pricing/)\.
- **Note**  
Each catcher can specify multiple errors to handle\.
- **Note**  
If you don't specify the `ResultPath` field, it defaults to `$`, which selects and overwrites the entire input\.
- **Note**  
When you create this Lambda function in the Lambda console, remember to change the **Timeout** value in the **Advanced settings** section from 3 seconds \(default\) to 11 seconds\.
- **Note**  
As a best practice, tasks that reference a Lambda function should handle Lambda service exceptions\. For more information, see [Handle Lambda service exceptions](bp-lambda-serviceexception.md)\.
- **Note**  
You can preserve the state input and the error by using `ResultPath`\. See [Use ResultPath to Include Both Error and Input in a `Catch`](input-output-resultpath.md#input-output-resultpath-catch)\.


## Tagging in Step Functions

- **Note**  
To manage tags for activites, see [Manage Tags with Step Functions API Actions](#tagging-api)\.

