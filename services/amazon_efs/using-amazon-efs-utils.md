---
id: Using amazon-efs-utils
title: Using amazon-efs-utils
created: 1683841041000
updated: 1683841041000
---
# Using amazon-efs-utils

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## Overview

- **Note**  
The `amzon-efs-utils` package comes preinstalled on Amazon Linux and Amazon Linux 2 Amazon Machine Images \(AMIs\)\.
- **Note**  
By default, when using the Amazon EFS mount helper with Transport Layer Security \(TLS\), the mount helper enforces certificate hostname checking\. The Amazon EFS mount helper uses the stunnel program for its TLS functionality\. Some versions of Linux don't include a version of stunnel that supports these TLS features by default\. When using one of those Linux versions, mounting an Amazon EFS file system using TLS fails\.  
When you've installed the amazon\-efs\-utils package, to upgrade your system's version of stunnel, see [Upgrading `stunnel`](upgrading-stunnel.md)\.  
You can use AWS Systems Manager to manage Amazon EFS clients and automate the tasks required to install or update the amazon\-efs\-utils package on your EC2 instances\. For more information, see [Using AWS Systems Manager to automatically install or update Amazon EFS clients](manage-efs-utils-with-aws-sys-manager.md)\.  
For issues with encryption, see [Troubleshooting Encryption](troubleshooting-efs-encryption.md)\.


## Manually installing the Amazon EFS client

- **Note**  
If you're using AWS Direct Connect, you can find installation instructions in [Walkthrough: Create and mount a file system on\-premises with AWS Direct Connect and VPN](efs-onpremises.md)\.


## Upgrading stunnel

- **Note**  
The default CentOS shell is csh, which has different syntax than the bash shell\. The following code first invokes bash, then moves `/bin/stunnel` to `/root`\.

