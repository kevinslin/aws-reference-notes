---
id: Configuring functions
title: Configuring functions
created: 1683841041000
updated: 1683841041000
---
# Configuring functions
{% hint style="info" %}
This page was generated from content adapted from [Dummy](https://docs.aws.amazon.com/ec2/index.html)
{% endhint %}
## Configuring function options

- **Note**  
 Configuring ephemeral storage past the default 512 MB allocated incurs a cost\. For more information, see [Lambda pricing](https://aws.amazon.com/lambda/pricing)\.
- **Note**  
Compute Optimizer supports only functions that use x86\_64 architecture\.


## Environment variables

- **Note**  
To increase database security, we recommend that you use AWS Secrets Manager instead of environment variables to store database credentials\. For more information, see [Configuring database access for a Lambda function](https://docs.aws.amazon.com/lambda/latest/dg/configuration-database.html)\.
- **Note**  
In some cases, you may need to use the following format:
- **Note**  
To increase database security, we recommend that you use AWS Secrets Manager instead of environment variables to store database credentials\. For more information, see [Configuring database access for a Lambda function](https://docs.aws.amazon.com/lambda/latest/dg/configuration-database.html)\.


## Versions

- **Note**  
Lambda doesn't create a new version if the code in the unpublished version is the same as the previous published version\. You need to deploy code changes in $LATEST before you can create a new version\.


## Creating layers

- **Note**  
For Node\.js runtimes, Lambda doesn't currently support ES module dependencies in layers\.
- **Note**  
Each time that you call `publish-layer-version`, you create a new version of the layer\.

