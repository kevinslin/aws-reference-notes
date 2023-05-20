---
id: Automate tasks
title: Automate tasks
created: 1683841041000
updated: 1683841041000
---
# Automate tasks

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## AWS CloudShell and the AWS CLI

- **Note**  
Your IAM identity also requires a policy that grants permission to make calls to AWS Control Tower\. For more information, see [Permissions required to use the AWS Control Tower console](https://docs.aws.amazon.com/controltower/latest/userguide/access-control-managing-permissions.html#additional-console-required-permissions)\.
- **Note**  
When using AWS CLI in AWS CloudShell, you don't need to download or install any additional resources\. You're already authenticated within the shell, so you don't need to configure credentials before making calls\.<a name="launch-cloudshell"></a>
- **Note**  
If you don't adhere to the [rules for naming buckets](https://docs.aws.amazon.com/AmazonS3/latest/dev/BucketRestrictions.html#bucketnamingrules) \(using only lowercase letters, for example\), the following error is displayed: An error occurred \(InvalidBucketName\) when calling the CreateBucket operation: The specified bucket is not valid\.


## AWS CloudFormation resources

- **Note**  
The limit for `EnableControl`and `DisableControl` updates in AWS Control Tower is 10 concurrent operations\.


## Resource identifiers for APIs and controls

- **Note**  
 The control **State** and status information is available in the console only\. It is not available from the public API\. To view the status of a control, navigate to the **Control details** page in the AWS Control Tower console\.

