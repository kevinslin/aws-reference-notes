---
id: Get started
title: Get started
created: 1683841041000
updated: 1683841041000
---
# Get started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/emp-user-guide.git)
{% endhint %}

## Package an application

- **Note**  
If the criteria for standard packaging is met, then we recommend that you apply this packaging model instead of the GRP packaging model\.
- **Note**  
This step is required only if there is a benefit to test the package in an on\-premises environment to validate that it works as expected before migrating the application to AWS, or if it is required to troubleshoot any issues\. It helps identify whether issues are the result of the AWS environment setup, the EMP package, or the target operating system\.


## Deploy an application

- **Note**  
If you do not specify a name when you create a profile, it will default to `default` by both the AWS CLI and AWS Tools for PowerShell\. You are not required to update the `metadata.json` file found in the root of the EMP package\. If you specify a new name for the profile at a later time, update the `AWSProfileName` property in the `metadata.json` file\.

