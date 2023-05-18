---
id: Authoring
title: Authoring
created: 1683841041000
updated: 1683841041000
---
# Authoring

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-sam-developer-guide.git)
{% endhint %}

## Validating AWS SAM template files

- **Note**  
The `sam validate` command requires AWS credentials to be configured\. For more information, see [Configuration and Credential Files](https://docs.aws.amazon.com/cli/latest/userguide/cli-config-files.html)\.


## Using nested applications

- **Note**  
The maximum number of applications that can be nested in a serverless application is 200\.  
The maximum number of parameters a nested application can have is 60\.
- **Important**  
Applications that contain nested applications hosted in the AWS Serverless Application Repository inherit the nested applications' sharing restrictions\.   
For example, suppose an application is publicly shared, but it contains a nested application that's only privately shared with the AWS account that created the parent application\. In this case, if your AWS account doesn't have permission to deploy the nested application, you aren't able to deploy the parent application\. For more information about permissions to deploy applications, see [Application Deployment Permissions](https://docs.aws.amazon.com/serverlessrepo/latest/devguide/serverless-app-consuming-applications.html#application-deployment-permissions) and [Publishing Applications](https://docs.aws.amazon.com/serverlessrepo/latest/devguide/serverless-app-publishing-applications.html) in the *AWS Serverless Application Repository Developer Guide*\.
- **Note**  
When you deploy an application that contains nested applications, you must acknowledge that\. You do this by passing CAPABILITY\_AUTO\_EXPAND to the [CreateCloudFormationChangeSet API](https://docs.aws.amazon.com/goto/WebAPI/serverlessrepo-2017-09-08/CreateCloudFormationChangeSet),or using the [https://docs.aws.amazon.com/cli/latest/reference/serverlessrepo/create-cloud-formation-change-set.html](https://docs.aws.amazon.com/cli/latest/reference/serverlessrepo/create-cloud-formation-change-set.html) AWS CLI command\.  
For more information about acknowledging nested applications, see [Acknowledging IAM Roles, Resource Policies, and Nested Applications when Deploying Applications](https://docs.aws.amazon.com/serverlessrepo/latest/devguide/acknowledging-application-capabilities.html) in the *AWS Serverless Application Repository Developer Guide*\.


## Orchestrating applications

- **Note**  
To manage AWS SAM templates that contain Step Functions state machines, you must use version 0\.52\.0 or later of the AWS SAM CLI\. To check which version you have, execute the command `sam --version`\.


## Code signing

- **Note**  
In order to successfully sign your code with the `sam package` or `sam deploy` commands, versioning must be enabled for the Amazon S3 bucket you use with these commands\. If you are using the Amazon S3 Bucket that AWS SAM creates for you, versioning is enabled automatically\. For more information about Amazon S3 bucket versioning and instructions for enabling versioning on an Amazon S3 bucket that you provide, see [Using versioning in Amazon S3 buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) in the *Amazon Simple Storage Service User Guide*\.
- **Note**  
In order to successfully sign your code with the `sam package` or `sam deploy` commands, versioning must be enabled for the Amazon S3 bucket you use with these commands\. If you are using the Amazon S3 Bucket that AWS SAM creates for you, versioning is enabled automatically\. For more information about Amazon S3 bucket versioning and instructions for enabling versioning on an Amazon S3 bucket that you provide, see [Using versioning in Amazon S3 buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html) in the *Amazon Simple Storage Service User Guide*\.

