---
id: Storage
title: Storage
created: 1683841041000
updated: 1683841041000
---
# Storage

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ec2-user-guide.git)
{% endhint %}

## Instance volume limits

- **Important**  
Attaching more than 40 volumes to a Linux instance is supported on a best effort basis only and is not guaranteed\.


## Root device volume

- **Important**  
Only the following instance types support an instance store volume as the root device: C3, D2, G2, I2, M3, and R3\.


## Block device mappings

- **Note**  
For M3 instances, you must specify instance store volumes in the block device mapping for the instance when you launch it\. When you launch an M3 instance, instance store volumes specified in the block device mapping for the AMI may be ignored if they are not specified as part of the instance block device mapping\.
- **Note**  
For instances launched before the release of the 2009\-10\-31 API, AWS can't display the block device mapping\. You must detach and reattach the volumes so that AWS can display the block device mapping\.


## Torn write prevention

- **Note**  
You do not need to disable I/O merging for MySQL and MariaDB workloads\.
- **Note**  
The command returns the vendor\-specific information in hex with ASCII interpretation\. You might need to build a tool, similar to `ebsnvme-id`, into your applications that can read and parse the output\.
- **Note**  
The bytes in the following table represent the offset in bytes from the beginning of the NVMe namespace vendor specific data\.
- **Note**  
There is no performance impact on workloads that do not support torn write prevention\. You do not need to make any changes for these workloads\.  
Workloads that do support torn write prevention, but are not configured to use it, continue to use the doublewrite buffer and do not receive any performance benefits\.
- **Note**  
For MySQL and MariaDB, you must use `-C 16384` to match the database page size\. Setting allocation granularity to a value other than a multiple of the page size can result in allocations that might be mismatched with torn write prevention boundaries of the storage device\.
- **Important**  
If you are using Logical Volume Manager \(LVM\) or other storage virtualization layer, make sure that the starting offsets of the volumes are aligned on 16 KiB multiples\. This is relative to the underlying NVMe storage to account for the metadata headers and superblocks used by the storage virtualization layer\. If you add an offset to the LVM physical volume, it can cause misalignment between the file system allocations and the NVMe device's offsets, which would invalidate torn write prevention\. For more information, see `--dataalignmentoffset` in the [Linux manual page](https://man7.org/linux/man-pages/man8/pvcreate.8.html)\.

