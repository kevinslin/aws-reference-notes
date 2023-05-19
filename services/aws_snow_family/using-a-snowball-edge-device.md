---
id: Using a Snowball Edge Device
title: Using a Snowball Edge Device
created: 1683841041000
updated: 1683841041000
---
# Using a Snowball Edge Device

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-snowball-developer-guide.git)
{% endhint %}

## Transferring Files Using the S3 adapter

- **Important**  
We recommend that you use only one method at a time to read and write data to a local bucket on an AWS Snowball Edge device\. Using both the file interface and the Amazon S3 adapter on the same bucket at the same time can result in read/write conflicts\.  
[Rate Limits on AWS Snowball Edge](rate-limiting.md) details the limits\.  
For AWS services to work properly on a Snowball Edge, you must allow the ports for the services\. For details, see [Ports Required to Use AWS Services on an AWS Snowball Edge Device](port-requirements.md)\.


## Transferring files using the File Interface

- **Note**  
If you created your job before July 17, 2018, this information doesn't apply to your device\. Instead, see [Transferring files using the Amazon S3 adapter for data migration](using-adapter.md)\.
- **Note**  
For best performance, use a Linux client to copy files to the Snowball Edge device\.
- **Important**  
For AWS services to work properly on a Snowball Edge device, you must allow the ports for the services\. For details, see [Ports Required to Use AWS Services on an AWS Snowball Edge Device](port-requirements.md)\.
- **Important**  
It can take an hour or more for the file interface to activate\. Don't power off or restart the device during this time\.
- **Note**  
For best performance, use a Linux client to copy files to the Snowball Edge device\.
- **Important**  
The IP address for the file interface is not the IP address that you used to unlock the Snowball Edge device\. The IP address for the file interface can either be a static IP or one issued by your DHCP server\.
- **Note**  
For a Windows 7 or Windows Server 2008 server, the maximum supported NFS I/O size is 32 KB\. Because of this limit, you might experience degraded performance for the file interface on these versions of Windows\.


## Using NFS for Offline Data Transfer

- **Note**  
File names are object keys in your local S3 bucket on the Snow Family device\. The key name is a sequence of Unicode characters whose UTF\-8 encoding is at most 1,024 bytes long\. We recommend using NFSv4\.1 where possible and encode file names with Unicode UTF\-8 to ensure a successful data import\. File names that are not encoded with UTF\-8 might not be uploaded to S3 or might be uploaded to S3 with a different file name depending on the NFS encoding you use\.  
Ensure that the maximum length of your file path is less than 1024 characters\. Snow Family devices do not support file paths that are greater that 1024 characters\. Exceeding this file path length will result in file import errors\.  
For more information, see [Object keys](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingMetadata.html#object-keys) in the *Amazon Simple Storage Service User Guide*\.
- **Note**  
You can only transfer up to 40M files using a single Snow Family device\. If you require to transfer more than 40M files in a single job, please batch the files in order to reduce the file numbers per each transfer\. Individual files can be of any size with a maximum file size of 5 TB for Snowball Edge devices with the NFS file interface and 150 GB for Snowball Edge devices with the S3 interface\.
You can provide CIDR blocks for IP ranges that are allowed to mount the NFS shares exposed by the device\. For example, `10.0.0.0/16`\. If you don't provide allowed CIDR blocks, all mount requests will be denied\. For details, see [ Restricting Access to NFS Shares When NFS is Running](https://docs.aws.amazon.com/snowball/latest/developer-guide/using-client-commands.html#sbe-restrict-access)\.
For NFS based transfers, standard POSIX style meta\-data will be added to your objects as they get imported to Amazon S3 from Snowball Edge\. In addition, you'll see meta\-data "x\-amz\-meta\-user\-agent aws\-datasync" as we currently use AWS DataSync as part of the internal import mechanism to Amazon S3 for Snowball Edge import with NFS option\.
- **Note**  
Check capacity of mounting point **/mnt/local** , shows near “80TB” available capacity for storage optimized Snow Family devices, as an example\. 
For more information, see [NFS data transfer for Storage Optimized devices](https://aws.amazon.com/about-aws/whats-new/2021/08/aws-snowball-edge-storage-optimized-nfs-data-transfer/)\.


## Using AWS IoT Greengrass on EC2 instances

- **Note**  
To install AWS IoT Greengrass Version 2 on a Snow Family device, make sure that your device is connected to the internet\. After installation, the internet is not required for a Snow Family device to work with AWS IoT Greengrass\.
- **Important**  
If your computer uses an earlier version of Microsoft Windows, you might not have the SSH command, or you might have SSH but can’t connect to your EC2 instance\. To connect to your EC2 instance, you can install and configure PuTTY, which is a no\-cost, open source SSH client\. You must convert the SSH key from `.pem` format to PuTTY format and connect to your EC2 instance\. For instructions on how to convert from `.pem` to PuTTY format, see the PuTTY documentation\.
- **Note**  
These are credentials from the IAM user in the AWS Region, not the Snow Family device\.
- **Note**  
This command is for an Amazon EC2 instance running an Amazon Linux 2 AMI\. For a Windows AMI, see [Install the AWS IoT Greengrass Core software](https://docs.aws.amazon.com/greengrass/v2/developerguide/install-greengrass-core-v2.html)\.


## Using Amazon EC2

- **Important**  
Using encrypted AMIs on Snowball Edge devices is not supported\.
Data in compute instances running on a Snowball Edge isn't imported into AWS\.


## Using IAM Locally

- **Important**  
The documentation in this section applies to using IAM locally on an AWS Snowball Edge device\. For information about using IAM in the AWS Cloud, see [Identity and Access Management in AWS Snowball](snowball-edge-iam.md)\.  
For AWS services to work properly on a Snowball Edge, you must allow the ports for the services\. For details, see [Ports Required to Use AWS Services on an AWS Snowball Edge Device](port-requirements.md)\.
- **Note**  
The access key ID and access secret key that are used locally on AWS Snowball Edge can't be interchanged with the keys in the AWS Cloud\.
- **Note**  
AWS Identity and Access Management \(IAM\) users need `"snowballdevice:*"` permissions to use the [AWS OpsHub for Snow Family application](aws-opshub.md) to manage Snow Family devices\.


## Using AWS STS

- **Important**  
For AWS services to work properly on a Snowball Edge, you must allow the ports for the services\. For details, see [Ports Required to Use AWS Services on an AWS Snowball Edge Device](port-requirements.md)\.
- **Note**  
The access key ID and access secret key that are use locally on AWS Snowball Edge can't be interchanged with the keys in the AWS Cloud\.

