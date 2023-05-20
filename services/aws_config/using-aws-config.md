---
id: Using AWS Config
title: Using AWS Config
created: 1683841041000
updated: 1683841041000
---
# Using AWS Config

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-config-developer-guide.git)
{% endhint %}

## AWS Config Dashboard

- **Note**  
The **Evaluate your AWS resource configuration using Config rules** message may appear on the **Dashboard** for the following reasons:  
You haven't set up AWS Config Rules for your AWS account\. You can choose **Add rule** to go to the **Rules** page\.
AWS Config is still evaluating your resources against your rules\. You can refresh the page to see the latest evaluation results\.
 AWS Config evaluated your resources against your rules and did not find any resources in scope\. You can specify the resources for AWS Config to record in the **Settings** page\. For more information, see [Selecting Which Resources AWS Config Records](select-resources.md)\.


## Record Configurations for Third-Party Resources

- **Note**  
If you have configured AWS Config to record all resource types, then third\-party resources that are managed \(created, updated, or deleted\) through AWS CloudFormation are automatically tracked in AWS Config as configuration items\.
- **Note**  
In order to guarantee that any project dependencies are correctly resolved, you can import the generated project into your IDE with Maven support\.  
For example, if you are using IntelliJ IDEA, you would need to do the following:  
From the **File** menu, choose **New**, then choose **Project From Existing Sources**\.
Navigate to the project directory
In the **Import Project** dialog box, choose **Import project from external model** and then choose **Maven**\.
Choose **Next** and accept any defaults to complete importing the project\.
- **Note**  
When using Maven, as part of the build process the `generate` command is automatically run before the code is compiled\. So your changes will never get out of sync with the generated code\.  
Be aware the CloudFormation CLI must be in a location Maven/the system can find\. For more information, see [Setting up your environment for developing extensions](https://docs.aws.amazon.com/cloudformation-cli/latest/userguide/what-is-cloudformation-cli.html#resource-type-setup)\.


## Advanced Queries

- **Note**  
Advanced queries supports a subset of the resource types supported by AWS Config\. For a list of those supported resource types, see [Supported Resource Types for Advanced Queries](https://github.com/awslabs/aws-config-resource-schema/tree/master/config/properties/resource-types)\.
- **Note**  
Advance query does not support querying resources which have not been configured to be recorded by the configuration recorder\. AWS Config creates Configuration Items \(CIs\) with `ResourceNotRecorded` in the `configurationItemStatus` when a resource has been discovered but is not configured to be recorded by the configuration recorder\. While an aggregator will aggregate these CIs, advanced query does not support querying CIs with `ResourceNotRecorded`\. Update your recorder settings to enable recording of the resource types that you want to query\.


## Tagging Your Resources

- **Note**  
`TagResource` and `UntagResource` require certain AWS Identity and Access Management \(IAM\) permissions to control access\. For more information, see [Controlling access based on tag keys](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_tags.html#access_tags_control-tag-keys) in the IAM User Guide\.

