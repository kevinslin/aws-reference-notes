---
id: Developing with Amazon S3
title: Developing with Amazon S3
created: 1683841041000
updated: 1683841041000
---
# Developing with Amazon S3

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Using the AWS CLI

- **Note**  
Services in AWS, such as Amazon S3, require that you provide credentials when you access them\. The service can then determine whether you have permissions to access the resources that it owns\. The console requires your password\. You can create access keys for your AWS account to access the AWS CLI or API\. However, we don't recommend that you access AWS using the credentials for your AWS account\. Instead, we recommend that you use AWS Identity and Access Management \(IAM\)\. Create an IAM user, add the user to an IAM group with administrative permissions, and then grant administrative permissions to the IAM user that you created\. You can then access AWS using a special URL and the credentials of that IAM user\. For instructions, go to [Creating Your First IAM user and Administrators Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html) in the *IAM User Guide*\.


## Error handling

- **Note**  
 SOAP support over HTTP is deprecated, but SOAP is still available over HTTPS\. New Amazon S3 features are not supported for SOAP\. Instead of using SOAP, we recommend that you use either the REST API or the AWS SDKs\.

