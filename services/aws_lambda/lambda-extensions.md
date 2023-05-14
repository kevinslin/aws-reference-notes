---
id: Lambda extensions
title: Lambda extensions
created: 1683841041000
updated: 1683841041000
---
# Lambda extensions
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}
## Extensions API

- **Note**  
For example extensions and wrapper scripts, see [AWS Lambda Extensions](https://github.com/aws-samples/aws-lambda-extensions) on the AWS Samples GitHub repository\.
- **Note**  
Extensions can complete their initialization at any point in the `Init` phase\.
- **Note**  
Lambda allocates CPU power in proportion to the function's memory setting\. You might see increased execution and initialization duration at lower memory settings because the function and extension processes are competing for the same CPU resources\. To reduce the execution and initialization duration, try increasing the memory setting\.
- **Note**  
Because the function code directory is read\-only, extensions cannot modify the function code\.


## Telemetry API

- **Important**  
The Lambda Telemetry API supersedes the Lambda Logs API\. **While the Logs API remains fully functional, we recommend using only the Telemetry API going forward\.** You can subscribe your extension to a telemetry stream using either the Telemetry API or the Logs API\. After subscribing using one of these APIs, any attempt to subscribe using the other API returns an error\.
- **Note**  
Lambda sends logs and metrics to CloudWatch, and traces to X\-Ray \(if you've activated tracing\), even if an extension subscribes to telemetry streams\.
- **Note**  
A Lambda function's execution environment can start and stop multiple times as part of its [lifecycle](runtimes-extensions-api.md#runtimes-extensions-api-lifecycle)\. In general, your extension code runs during function invocations, and also up to 2 seconds during the shutdown phase\. We recommend batching the telemetry as it arrives to your listener, and using the `Invoke` and `Shutdown` lifecycle events to dispatch each batch to their desired destinations\.
- **Note**  
We strongly recommend using HTTP rather than TCP\. With TCP, the Lambda platform cannot acknowledge when it delivers telemetry to the application layer\. Therefore, if your extension crashes, you might lose telemetry\. HTTP does not have this limitation\.

