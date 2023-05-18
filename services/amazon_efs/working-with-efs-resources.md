---
id: Working with EFS resources
title: Working with EFS resources
created: 1683841041000
updated: 1683841041000
---
# Working with EFS resources

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## Creating a file system

- **Note**  
For file systems that use One Zone storage classes, only the General Purpose performance mode is available\.
- **Note**  
Additional charges are associated with using Provisioned Throughput mode\. For more information, see [Amazon EFS pricing](http://aws.amazon.com/efs/pricing/)\.


## Deleting a file system

- **Note**  
You cannot delete a file system that is part of an EFS Replication configuration\. You need to delete the replication configuration first\. For more information, see [Deleting a replication configuration](efs-replication.md#delete-replications)\.
- **Important**  
You should always unmount a file system before you delete it\.


## Mount targets and security groups

- **Note**  
For file systems that use One Zone storage classes, you can only create a single mount target that is in the same Availability Zone as the file system\.


## Creating security groups

- **Note**  
The following section is specific to Amazon EC2 and discusses how to create security groups so you can use Secure Shell \(SSH\) to connect to any instances that have mounted Amazon EFS file systems\. If you're not using SSH to connect to your Amazon EC2 instances, you can skip this section\.


## Creating file system policies

- **Note**  
Amazon EFS file system policy changes can take several minutes to take effect\.

