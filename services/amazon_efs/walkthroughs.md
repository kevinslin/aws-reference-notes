---
id: Walkthroughs
title: Walkthroughs
created: 1683841041000
updated: 1683841041000
---
# Walkthroughs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## Walkthrough: Create and mount a file system using the AWS CLI

- **Note**  
This walkthrough is similar to the Getting Started exercise\. In the [Getting started](getting-started.md) exercise, you use the console to create EC2 and Amazon EFS resources\. In this walkthrough, you use the AWS CLI to do the same—primarily to familiarize yourself with the Amazon EFS API\.


## Walkthrough: Set up an Apache web server and serve files

- **Note**  
For both procedures, you create all resources in the US West \(Oregon\) Region \(`us-west-2`\)\.
- **Note**  
This setup does not configure the EC2 instance to automatically start httpd \(web server\) on boot, and also does not mount the file system on boot\. In the next walkthrough, you create a launch configuration to set this up\.


## Walkthrough: Create writable per-user subdirectories

- **Note**  
You can follow the [Getting started](getting-started.md) exercise to create and mount an Amazon EFS file system on your EC2 instance\.


## Walkthrough: Mount EFS on an on-premises client

- **Note**  
Using Amazon EFS with Microsoft Windows–based clients isn't supported\.
- **Note**  
In some cases, your local application might need to know if the EFS file system is available\. In these cases, your application should be able to point to a different mount point IP address if the first mount point becomes temporarily unavailable\. In this scenario, we recommend that you have two on\-premises clients connected to your file system through different Availability Zones \(AZs\) for higher availability\.
- **Note**  
If you haven't already, install the rpm\-builder package with the following command\.


## Walkthrough: Mount a File System from a Different VPC

- **Note**  
Using Amazon EFS with Microsoft Windows–based clients isn't supported\.


## Walkthrough: Enforcing Encryption on an Amazon EFS File System at Rest

- **Note**  
The method for enforcing the creation of Amazon EFS file systems that are encrypted at rest described in this walkthrough is deprecated\. The preferred method to enforce the creation of file systems that are encrypted at rest is to use the `elasticfilesystem:Encrypted` condition key in AWS Identity and Access Management identity\-based policies\. For more information, see [Using IAM to enforce creating encrypted file systems](using-iam-to-enforce-encryption-at-rest.md)\. You can use this walkthrough to create CloudWatch alarms to validate that your IAM policies are preventing the creation of unencrypted file systems\.

