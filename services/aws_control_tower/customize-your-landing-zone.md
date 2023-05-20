---
id: Customize your landing zone
title: Customize your landing zone
created: 1683841041000
updated: 1683841041000
---
# Customize your landing zone

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## Deployment considerations

- **Note**  
The sample configuration package filename begins with an underscore \(\_\) so that AWS CodePipeline is not initiated automatically\. When you have finished customizing the configuration package, be sure to upload the `custom-control-tower-configuration.zip` without the underscore \(\_\) in order to begin the deployment in AWS CodePipeline\.
- **Note**  
When you're using the default S3 bucket, be sure that the configuration package is available as a `.zip` file\. When you're using the AWS CodeCommit repository, be sure that the configuration package is placed in the repository without zipping the files\. For information about creating and storing the configuration package in AWS CodeCommit, see [CfCT customization guide](cfct-customizations-dev-guide.md)\.
- **Note**  
When you're using AWS CodeCommit to store the configuration package, it is not necessary to zip the package\. For information about creating and storing the configuration package in AWS CodeCommit, refer to [CfCT customization guide](cfct-customizations-dev-guide.md)\.


## Template and source code

- **Note**  
 You can customize the template based on your specific requirements\.


## Deploy CfCT

- **Important**  
To download the correct AWS CloudFormation template and launch CfCT, follow the GitHub link given in this section\. Do not follow older links to any previously specified S3 buckets\.


## Set up Amazon S3 as the configuration source

- **Note**  
If you choose to download and modify this file, remember to zip the changes, save as a new file named `custom-control-tower-configuration.zip`, and then upload it back to the same Amazon S3 bucket\.  
The Amazon S3 bucket is the default source of the pipeline\. When default settings are in place, uploading a configuration zip file without the underscore prefix in the file name to the S3 bucket will initiate the pipeline automatically\.


## Operational metrics

- **Note**  
 AWS owns the data it collects\. Data collection is subject to the [AWS Privacy Policy](https://aws.amazon.com/privacy/)\.


## CfCT customization guide

- **Note**  
 To deploy and configure \(CfCT\), you must deploy and process a configuration package through AWS CodePipeline\. The following sections describe the process in detail\.

