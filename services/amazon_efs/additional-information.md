---
id: Additional information
title: Additional information
created: 1683841041000
updated: 1683841041000
---
# Additional information

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## Back up with AWS Data Pipeline

- **Note**  
Using the AWS Data Pipeline to back up your EFS file systems is a legacy solution\.
- **Important**  
This solution requires using AWS Data Pipeline in the same AWS Region as your file system\. Because AWS Data Pipeline is not supported in US East \(Ohio\), this solution doesn't work in that AWS Region\. We recommend that if you want to back up your file system using this solution, you use your file system in one of the other supported AWS Regions\.
- **Note**  
This template also references and runs a script to perform the backup commands\. You can download the script before creating the pipeline to review what it does\. To review the script, download [efs\-backup\.sh](https://github.com/awslabs/data-pipeline-samples/blob/master/samples/EFSBackup/efs-backup.sh) from GitHub\. This backup solution depends on running scripts that are hosted on GitHub and is subject to GitHub availability\. If you'd prefer to eliminate this reliance and host the scripts in an Amazon S3 bucket instead, see [Hosting the rsync scripts in an Amazon S3 bucket](#hostingscripts)\.
- **Important**  
If you're using additional nodes, you can't use spaces in file names and directories stored in the top\-level directory\. If you do, those files and directories aren't backed up or restored\. All files and subdirectories that are at least one level below the top level are backed up and restored as expected\.


## Mounting file systems without the EFS mount helper

- **Note**  
In this section, you can learn how to mount your Amazon EFS file system without the amazon\-efs\-utils package\. To use encryption of data in transit with your file system, you must mount your file system with Transport Layer Security \(TLS\)\. To do so, we recommend using the amazon\-efs\-utils package\. For more information, see [Using the amazon\-efs\-utils Tools](using-amazon-efs-utils.md)\.
- **Note**  
Before you can mount a file system, you must create, configure, and launch your related AWS resources\. For detailed instructions, see [Getting started with Amazon Elastic File System](getting-started.md)\.
- **Note**  
Prior to mounting your file system, you need to create VPC security groups for your Amazon EC2 instances and mount targets with the required inbound and outbound access\. For more information, see [Using VPC security groups for Amazon EC2 instances and mount targets](network-access.md)\.
- **Note**  
For Linux kernel versions 5\.4\.\*, the Linux NFS client uses a default `read_ahead_kb` value of 128 KB\. We recommend increasing this value to 15 MB\. For more information, see [Optimizing the NFS read\_ahead\_kb size](performance-tips.md#efs-perf-optimize-nfs-read-ahead)\.
- **Note**  
RHEL 6\.9 might be suboptimal for certain workloads due to [Poor Performance When Opening Many Files in Parallel](troubleshooting-efs-general.md#open-close-operations-serialized)\.
- **Note**  
Using Amazon EFS with Amazon EC2 instances running Microsoft Windows is not supported\.
- **Note**  
If you choose **Amazon Linux AMI 2016\.03\.0** or **Amazon Linux AMI 2016\.09\.0** when launching your Amazon EC2 instance, you don't need to install `nfs-utils` because it's already included in the AMI by default\.

