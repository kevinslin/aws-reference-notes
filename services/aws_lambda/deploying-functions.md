---
id: Deploying functions
title: Deploying functions
created: 1683841041000
updated: 1683841041000
---
# Deploying functions
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}
## .zip file archives

- **Note**  
You cannot convert an existing container image function to use a \.zip file archive\. You must create a new function\.
- **Note**  
The Lambda console uses AWS Cloud9 to provide an integrated development environment in the browser\. You can also use AWS Cloud9 to develop Lambda functions in your own environment\. For more information, see [Working with Lambda Functions](https://docs.aws.amazon.com/cloud9/latest/user-guide/lambda-functions.html) in the AWS Cloud9 user guide\.


## Container images

- **Note**  
You cannot convert an existing container image function to use a \.zip file archive\. You must create a new function\.
- **Note**  
On Windows, some Bash CLI commands that you commonly use with Lambda \(such as `zip`\) are not supported by the operating system's built\-in terminals\. To get a Windows\-integrated version of Ubuntu and Bash, [install the Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)\.
- **Note**  
For the override settings, make sure that you enclose each string in quotation marks \(" "\)\.
- **Note**  
You cannot change the `package-type` of a function\.
- **Note**  
If you declare an `ImageConfig` property in your AWS CloudFormation template, you must provide values for all three of the `ImageConfig` properties\.

