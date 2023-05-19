---
id: X-Ray API
title: X-Ray API
created: 1683841041000
updated: 1683841041000
---
# X-Ray API

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-xray-developer-guide.git)
{% endhint %}

## Tutorial

- **Note**  
You must verify that your AWS CLI is configured to the same Region that your Scorekeep sample application was created in\.


## Sending data

- **Note**  
Windows Command Processor and Windows PowerShell have different requirements for quoting and escaping quotes in JSON strings\. See [Quoting Strings](https://docs.aws.amazon.com/cli/latest/userguide/cli-using-param.html#quoting-strings) in the AWS CLI User Guide for details\.
- **Note**  
See [Running the X\-Ray daemon locally](xray-daemon-local.md) for instructions on running the daemon\.


## Configuration

- **Note**  
X\-Ray does not support asymmetric KMS keys\.


## Sampling

- **Note**  
The response from X\-Ray might not include a quota the first time you call it\. Continue borrowing from the reservoir until you are assigned a quota\.


## Segment documents

- **Note**  
Values must be strings \(up to 250 characters\) unless noted otherwise\.
- **Note**  
Values are strings up to 250 characters unless noted otherwise\.

