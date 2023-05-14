---
id: Managing functions
title: Managing functions
created: 1683841041000
updated: 1683841041000
---
# Managing functions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}

## Tutorial - Lambda with CLI

- **Note**  
On Windows, some Bash CLI commands that you commonly use with Lambda \(such as `zip`\) are not supported by the operating system's built\-in terminals\. To get a Windows\-integrated version of Ubuntu and Bash, [install the Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)\.


## Networking

- **Tip**  
If your function already includes a VPC configuration from a previous API request, you can send an `UpdateFunctionConfiguration` request without the VPC configuration\.
- **Note**  
Several AWS services offer [VPC endpoints](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html)\. You can use VPC endpoints to connect to AWS services from within a VPC without internet access\.


## Interface VPC endpoints

- **Note**  
You need to include both the qualified and the unqualified function ARN in the resource\.


## File system

- **Note**  
When you create a file system, you choose a performance mode that can't be changed later\. **General purpose** mode has lower latency, and **Max I/O** mode supports a higher maximum throughput and IOPS\. For help choosing, see [Amazon EFS performance](https://docs.aws.amazon.com/efs/latest/ug/performance.html) in the *Amazon Elastic File System User Guide*\.
- **Note**  
If your function is not already connected to a VPC, see [Configuring a Lambda function to access resources in a VPC](configuration-vpc.md)\.


## Code signing

- **Note**  
Functions defined as container images do not support code signing\.


## Using layers

- **Note**  
Make sure that the layers that you add to a function are compatible with the runtime and instruction set architecture of the function\.

