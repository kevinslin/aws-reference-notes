---
id: Using AWS OpsHub to Manage Devices
title: Using AWS OpsHub to Manage Devices
created: 1683841041000
updated: 1683841041000
---
# Using AWS OpsHub to Manage Devices

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-snowball-developer-guide.git)
{% endhint %}

## Managing Your Devices

- **Important**  
We highly recommend that you suspend all activities on the device before you reboot the device\. Rebooting a device stops running instances, interrupts any writing to Amazon S3 buckets on the device, and stops any write operations from the file interface without clearing the cache\.
- **Important**  
We highly recommend that you suspend all activities on the device before you shut down the device\. Shutting down a device stops running instances, interrupts any writing to Amazon S3 buckets on the device, and stops any write operations from the file interface without clearing the cache\.


## Automating Your Management Tasks

- **Note**  
Automating tasks is not supported on clusters\.  
To use tasks, the Amazon EC2 Systems Manager service must be started first\. To start a service on your Snowball Edge, see [Starting a Service on Your Snowball Edge](using-client-commands.md#edge-start-service)\.

