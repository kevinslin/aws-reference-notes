---
id: Transferring your data
title: Transferring your data
created: 1683841041000
updated: 1683841041000
---
# Transferring your data

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-datasync-user-guide.git)
{% endhint %}

## Where can I transfer my data?

- **Important**  
You pay for data transferred between AWS Regions\. This transfer is billed as data transfer OUT from the source to destination Region\. For more information, see [Data transfer pricing](http://aws.amazon.com/ec2/pricing/on-demand/#Data_Transfer)\.


## How DataSync handles metadata and special files

- **Note**  
HDFS uses strings to store file and folder user and group ownership, rather than numeric identifiers \(such as UIDs and GIDs\)\. When copying from HDFS to Amazon EFS, FSx for Lustre, FSx for OpenZFS, or FSx for ONTAP \(using NFS\), default values for UIDs and GIDs are applied on the destination file system\. For more information about default values, see [Default POSIX metadata applied by DataSync](#POSIX-metadata)\.
- **Note**  
HDFS uses strings to store file and folder user and group ownership, rather than numeric identifiers, such as UIDs and GIDs\. DataSync ignores user and group name metadata values stored in Amazon S3 when copying to Amazon EFS or self\-managed NFS\.
- **Important**  
If you're transferring objects from a Google Cloud Storage bucket, copying object tags may cause your DataSync task to fail\. To prevent this, deselect the **Copy object tags** option when configuring your task settings\. For more information, see [File metadata and management options](create-task.md#configure-file)\.

