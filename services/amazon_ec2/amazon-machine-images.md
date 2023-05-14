---
id: Amazon Machine Images
title: Amazon Machine Images
created: 1683841041000
updated: 1683841041000
---
# Amazon Machine Images
{% hint style="info" %}
This page was generated from content adapted from [Dummy](https://docs.aws.amazon.com/ec2/index.html)
{% endhint %}
## Find a Linux AMI

- **Important**  
Omitting the `--owners` flag from the describe\-images command returns all images for which you have launch permissions, regardless of ownership\.
- **Note**  
Running instances are not affected when you change the AMI ID pointed to by the Systems Manager parameter\.


## Paid AMIs

- **Important**  
Amazon DevPay is no longer accepting new sellers or products\. AWS Marketplace is now the single, unified e\-commerce platform for selling software and services through AWS\. For information about how to deploy and sell software from AWS Marketplace, see [Selling in AWS Marketplace](http://aws.amazon.com/marketplace/partners/management-tour)\. AWS Marketplace supports AMIs backed by Amazon EBS\.
- **Important**  
You can't use a support product with Reserved Instances\. You always pay the price that's specified by the seller of the support product\.


## Use encryption with EBS-backed AMIs

- **Note**  
Enabling [encryption by default](EBSEncryption.md#encryption-by-default) has the same effect as setting the `Encrypted` parameter to `true` for all snapshots in the AMI\.
- **Note**  
You can also copy an image with multiple snapshots and configure the encryption state of each individually\.


## Amazon Linux

- **Important**  
Your instance must have access to the internet in order to access the repository\.
- **Important**  
If you lock to a version of the repositories that is not the latest, you do not receive further updates\. To receive a continuous flow of updates, you must use the latest AMI, or consistently update your AMI with the repositories pointed to latest\.
- **Note**  
This command does not remove packages that were installed as dependencies of the extra\.
- **Important**  
This command is intended for advanced users\. Improper usage of this command could cause package compatibility conflicts\.


## User provided kernels

- **Note**  
We continue to provide hd00 AKIs for backward compatibility in Regions where they were previously available\.


## Configure the MATE desktop connection

- **Important**  
`xrdp` is the remote desktop software bundled in the AMI\. By default, `xrdp` uses a self\-signed TLS certificate to encrypt remote desktop sessions\. Neither AWS nor the `xrdp` maintainers recommend using self\-signed certificates in production\. Instead, obtain a certificate from an appropriate certificate authority \(CA\) and install it on your instances\. For more information about TLS configuration, see [TLS security layer](https://github.com/neutrinolabs/xrdp/wiki/TLS-security-layer) on the `xrdp` wiki\.
- **Note**  
This command generates a certificate that is valid for 365 days\.

