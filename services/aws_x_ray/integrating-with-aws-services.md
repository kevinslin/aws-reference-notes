---
id: Integrating with AWS services
title: Integrating with AWS services
created: 1683841041000
updated: 1683841041000
---
# Integrating with AWS services

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-xray-developer-guide.git)
{% endhint %}

## API Gateway

- **Note**  
X\-Ray only supports tracing for REST APIs through API Gateway\.
- **Note**  
When tracing REST APIs with API Gateway [HTTP integration](https://docs.aws.amazon.com/apigateway/latest/developerguide/setup-http-integrations.html), each segment's service name is set to the request URL path from API Gateway to your HTTP integration endpoint, resulting in a service node on the X\-Ray service map for each unique URL path\. A large number of URL paths may cause the service map to exceed the limit of 10,000 nodes, resulting in an error\.  
To minimize the number of service nodes created by API Gateway, consider passing parameters within the URL query string or in the request body via POST\. Either approach will ensure parameters are not part of the URL path, which may result in fewer distinct URL paths and service nodes\.


## App Mesh

- **Note**  
The App Mesh version of Envoy does not currently send traces based on configured [sampling rules](https://docs.aws.amazon.com/xray/latest/devguide/xray-console-sampling.html)\. Instead, it uses a fixed sampling rate of 5% for Envoy version 1\.16\.3 or newer, or a 50% sampling rate for Envoy versions prior to 1\.16\.3\.
- **Note**  
To learn more about available Envoy region addresses, see [Envoy image](https://docs.aws.amazon.com/app-mesh/latest/userguide/envoy.html) in the AWS App Mesh User Guide\.


## Step Functions

- **Note**  
When you create a new state machine, it's automatically traced if the request is sampled and tracing is enabled in an upstream service such as Amazon API Gateway or AWS Lambda\. For any existing state machine not configured through the console, for example through an AWS CloudFormation template, check that you have an IAM policy that grants sufficient permissions to enable X\-Ray traces\.

