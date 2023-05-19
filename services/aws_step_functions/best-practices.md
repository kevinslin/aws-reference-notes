---
id: Best practices
title: Best practices
created: 1683841041000
updated: 1683841041000
---
# Best practices

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## Use timeouts to avoid stuck executions

- **Note**  
You can set a timeout for your state machine using the `TimeoutSeconds` field in your Amazon States Language definition\. For more information, see [State Machine Structure](amazon-states-language-state-machine-structure.md)\.


## Use Amazon S3 ARNs instead of passing large payloads

- **Note**  
After you create this Lambda function, make sure you provide its IAM role the appropriate permission to read from an Amazon S3 bucket\. For example, attach the **AmazonS3ReadOnlyAccess** permission to the Lambda function's role\.


## Handle Lambda service exceptions

- **Note**  
Unhandled errors in Lambda are reported as `Lambda.Unknown` in the error output\. These include out\-of\-memory errors and function timeouts\. You can match on `Lambda.Unknown`, `States.ALL`, or `States.TaskFailed` to handle these errors\. When Lambda hits the maximum number of invocations, the error is `Lambda.TooManyRequestsException`\. For more information about Lambda function errors, see [Error handling and automatic retries](https://docs.aws.amazon.com/lambda/latest/dg/invocation-retries.html) in the *AWS Lambda Developer Guide*\.

