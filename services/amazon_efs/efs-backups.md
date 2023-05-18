---
id: EFS backups
title: EFS backups
created: 1683841041000
updated: 1683841041000
---
# EFS backups

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## AWS Backup and EFS

- **Note**  
Automatic backups are exempt from the AWS Backup service opt\-out configuration\. For more information, see [ Getting Started with AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/getting-started.html) in the *AWS Backup Developer Guide*\.
- **Note**  
Sockets and named pipes are not supported, and are omitted from backups\.
- **Note**  
 To restore a recovery point, users must have the `backup:StartRestoreJob` permission\.
- **Note**  
For Partial restores to an existing EFS file system, AWS Backup restores the files and directories to a new directory under the file system root directory\. The full hierarchy of the specified items is preserved in the recovery directory\. For example, if directory A contains subdirectories B, C, and D, AWS Backup retains the hierarchical structure when A, B, C, and D are recovered\.

