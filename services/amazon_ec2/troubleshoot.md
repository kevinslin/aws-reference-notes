---
id: Troubleshoot
title: Troubleshoot
created: 1683841041000
updated: 1683841041000
---
# Troubleshoot
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ec2-user-guide.git)
{% endhint %}
## Connect to your instance

- **Note**  
If you get an error stating that the file system is corrupt, run the following command to use the **fsck** utility to check the file system and repair any issues:
- **Note**  
If the name of your new key pair and corresponding private key file is different from the name of the original key pair, ensure that you specify the name of the new private key file when you connect to your instance\.


## Stop your instance

- **Note**  
You can force an instance to stop using the console only while the instance is in the `stopping` state\. You can force an instance to stop using the AWS CLI while the instance is in any state, except `shutting-down` and `terminated`\.
- **Important**  
Creating a replacement instance is recommended if it's registering [system status checks](monitoring-instances-status-check.md) only, as instance status checks will result in the AMI copying over an exact replica of the broken OS\. Once you've confirmed the status message, create the AMI and launch a new instance using the new AMI\.


## Troubleshoot an unreachable instance

- **Note**  
Only the most recent 64 KB of posted output is stored, which is available for at least 1 hour after the last posting\.


## Boot from the wrong volume

- **Important**  
If you intend to detach the volume with the new label and return it to another instance to use as the root volume, you must perform the above procedure again and change the volume label back to its original value\. Otherwise, the other instance does not boot because the ramdisk is unable to find the volume with the label `/`\.


## Send a diagnostic interrupt

- **Note**  
By default, the crash dump file is saved to `/var/crash/`\. To change the location, modify the `/etc/kdump.conf` file using your preferred text editor\.
- **Note**  
By default, the crash dump file is saved to `/var/crash/`\. To change the location, modify the `/etc/kdump.conf` file using your preferred text editor\.
- **Note**  
On instances based on Intel and AMD processors, the `send-diagnostic-interrupt` command sends an *unknown non\-maskable interrupt* \(NMI\) to the instance\. You must configure the kernel to crash when it receives the unknown NMI\. Add the following to your configuration file\.

