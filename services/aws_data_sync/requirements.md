---
id: Requirements
title: Requirements
created: 1683841041000
updated: 1683841041000
---
# Requirements

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-datasync-user-guide.git)
{% endhint %}

## Agent requirements

- **Note**  
An exception to this recommendation is if you're running DataSync on an AWS Snowcone device\. Use the default instance snc1\.medium, which provides 2 CPU cores and 4 GiB of memory\.


## Network requirements

- **Note**  
Depending on your network, you might need to allow traffic on ports other than what's listed here for DataSync to connect with your self\-managed storage\.
- **Note**  
The total number of network interfaces depends on your DataSync task locations\. For example, transferring from an Amazon EFS location to FSx for Lustre requires four network interfaces\. Meanwhile, transferring from an FSx for Windows File Server to an Amazon S3 bucket requires two network interfaces\.

