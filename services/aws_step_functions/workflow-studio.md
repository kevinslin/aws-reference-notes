---
id: Workflow Studio
title: Workflow Studio
created: 1683841041000
updated: 1683841041000
---
# Workflow Studio

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## Configure input and output

- **Note**  
To specify that a parameter uses a reference path to point to a JSON node in the input, the parameter name must end with `.$`\.
- **Note**  
To specify that a parameter uses a path to reference a JSON node in the result, the parameter name must end with `.$`\.
- **Note**  
Since the `OutputPath` filter is the last output filter to take effect, if you use additional output filters such as `ResultSelector` or `ResultPath`, you should modify the default `$.Payload` `OutputPath` filter accordingly\.


## Error handling

- **Note**  
Not all error handling options are available for all states\. Lambda Invoke has one retrier configured by default\.


## Tutorial: Learn to use the AWS Step Functions Workflow Studio

- **Note**  
Before you start, make sure to complete the [prerequisites for this tutorial](sfn-prerequisites.md)\.
- **Note**  
While specifying an execution input is optional, in this tutorial, it is mandatory to specify an execution input similar to the above example input\. This input value is referenced in the `Choice` state when you run the state machine\.


## Known limitations

- **Note**  
State machine definitions that contain AWS CloudFormation references cannot be saved\. However, you can copy or export the definition for use elsewhere\.

