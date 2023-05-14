---
id: Lambda foundations
title: Lambda foundations
created: 1683841041000
updated: 1683841041000
---
# Lambda foundations
{% hint style="info" %}
This page was generated from content adapted from [Dummy](https://docs.aws.amazon.com/ec2/index.html)
{% endhint %}
## Programming model

- **Note**  
Logging is subject to [CloudWatch Logs quotas](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/cloudwatch_limits_cwl.html)\. Log data can be lost due to throttling or, in some cases, when an instance of your function is stopped\.


## Execution environment

- **Note**  
The Lambda reset does not clear the `/tmp` directory content prior to the next init phase\. This behavior is consistent with the regular shutdown phase\.


## Deployment packages

- **Note**  
Container images aren't supported for Lambda functions in the Middle East \(UAE\) Region\.


## Instruction sets (ARM/x86)

- **Note**  
Runtimes that use the Amazon Linux operating system, such as Go 1\.x, do not support the arm64 architecture\. To use arm64 architecture, you can run Go with the provided\.al2 runtime\. For example, see [Build a Go function for the provided\.al2 runtime](golang-package.md#golang-package-al2) or [Create a Go image from the provided\.al2 base image](go-image.md#go-image-al2)\.

