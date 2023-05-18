---
id: Managing file systems
title: Managing file systems
created: 1683841041000
updated: 1683841041000
---
# Managing file systems

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## Managing mount targets

- **Note**  
We recommend that you create a mount target in each of the Availability Zones\. There are cost considerations for mounting a file system on an EC2 instance in an Availability Zone through a mount target created in another Availability Zone\. For more information, see [Amazon EFS](https://aws.amazon.com/efs/)\. In addition, by always using a mount target local to the instance's Availability Zone, you eliminate a partial failure scenario\. If the mount target's zone goes down, you can't access your file system through that mount target\.
- **Note**  
Before deleting a mount target, first unmount the file system\. For more information, see [Unmounting file systems](mounting-fs-mount-cmd-general.md#unmounting-fs)\.
- **Note**  
Before deleting a mount target, first unmount the file system\.


## Managing throughput

- **Note**  
You can decrease your file system throughput in *Provisioned Throughput* mode as long as it’s been more than 24 hours since the last decrease\. Additionally, you can change between *Provisioned Throughput* mode and the default *Bursting Throughput* mode as long as it’s been more than 24 hours since the last throughput mode change\.


## File system metering

- **Note**  
The computed metered size doesn't represent a consistent snapshot of the file system at any particular time during that hour\. Instead, it represents the sizes of the objects that existed in the file system at varying times within each hour, or possibly the hour before it\. These sizes are summed to determine the file system's metered size for the hour\. The metered size of a file system is thus eventually consistent with the metered sizes of the objects stored when there are no writes to the file system\.
- **Note**  
The metered size of `ValueInStandard` is also used to determine your I/O throughput baseline and burst rates\. For more information, see [Bursting Throughput mode](performance.md#bursting)\.

