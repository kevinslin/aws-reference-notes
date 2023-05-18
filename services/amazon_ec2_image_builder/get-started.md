---
id: Get started
title: Get started
created: 1683841041000
updated: 1683841041000
---
# Get started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/ec2-image-builder-user-guide.git)
{% endhint %}

## Prerequisites

- **Note**  
If you want to copy an image created with Image Builder to another account, you must create the `EC2ImageBuilderDistributionCrossAccountRole` role in all of the target accounts, and attach the [Ec2ImageBuilderCrossAccountDistributionAccess policy](security-iam-awsmanpol.md#sec-iam-manpol-Ec2ImageBuilderCrossAccountDistributionAccess) managed policy to the role\. For more information, see [Share EC2 Image Builder resources](manage-shared-resources.md)\.


## Create an image pipeline (AMI)

- **Note**  
To specify a subnet to use for a private VPC, you can create your own custom infrastructure configuration, or use settings that you have already created\.
- **Tip**  
To prevent dependency errors when you delete resources, make sure to delete your resources in the following order:  
Image pipeline
Image recipe
All remaining resources


## Create an image pipeline (Docker)

- **Tip**  
To prevent dependency errors when you delete resources, make sure to delete your resources in the following order:  
Image pipeline
Image recipe
All remaining resources

