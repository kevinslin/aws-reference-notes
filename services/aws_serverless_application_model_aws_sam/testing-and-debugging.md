---
id: Testing and debugging
title: Testing and debugging
created: 1683841041000
updated: 1683841041000
---
# Testing and debugging

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-sam-developer-guide.git)
{% endhint %}

## Invoking functions locally

- **Note**  
The sam local invoke command corresponds to the AWS Command Line Interface \(AWS CLI\) command [https://awscli.amazonaws.com/v2/documentation/api/latest/reference/lambda/invoke.html](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/lambda/invoke.html)\. You can use either command to invoke a Lambda function\.


## Running API Gateway locally

- **Note**  
*Hot reloading* is when only the files that changed are refreshed, and the state of the application remains the same\. In contrast, *live reloading* is when the entire application is refreshed, and the state of the application is lost\.


## Step-through debugging Lambda functions locally

- **Note**  
If you're using `sam local start-api`, the local API Gateway instance exposes all of your Lambda functions\. However, because you can specify a single debug port, you can only debug one function at a time\. You need to call your API before the AWS SAM CLI binds to the port, which allows the debugger to connect\.

