---
id: Mounting file systems
title: Mounting file systems
created: 1683841041000
updated: 1683841041000
---
# Mounting file systems

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## Mounting with EFS mount helper

- **Note**  
Amazon EFS does not support mounting from Amazon EC2 Windows instances\.
- **Note**  
The watchdog process ensures that each mount's stunnel process is running, and stops the stunnel when the Amazon EFS file system is unmounted\. If for some reason a stunnel process is terminated unexpectedly, the watchdog process restarts it\.
- **Important**  
You can enable logging for the stunnel process logs\. However, enabling the stunnel logs can use up a nontrivial amount of space on your file system\.
- **Note**  
Amazon EFS file systems do not support automatic mounting on Amazon EC2 Mac instances running macOS Big Sur\.
- **Note**  
Amazon EFS file systems do not support mounting on Amazon EC2 Mac instances running macOS Big Sur at instance launch\.
- **Note**  
You can't use Amazon EFS with Microsoft Windows–based Amazon EC2 instances\.
- **Note**  
Amazon EFS file systems do not support automatic mounting using `/etc/fstab` on Amazon EC2 Mac instances running macOS Big Sur\.
- **Note**  
Before you can update the `/etc/fstab` file of your EC2 instance, make sure that you already created your Amazon EFS file system\. For more information, see [Step 1: Create your Amazon EFS file system](gs-step-two-create-efs-resources.md)\.
- **Note**  
In some cases, your Amazon EC2 instance might need to start regardless of the status of your mounted Amazon EFS file system\. In such cases, add the `nofail` option to your file system's entry in your `/etc/fstab` file\.


## Additional mounting considerations

- **Note**  
If your EC2 instance needs to start regardless of the status of your mounted EFS file system, add the `nofail` option to your file system's entry in your `/etc/fstab` file\.


## Troubleshooting AMI and kernel versions

- **Note**  
Amazon EFS does not support mounting from Amazon EC2 Windows instances\.

