---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-efs-user-guide.git)
{% endhint %}

## Controlling file system data access

- **Important**  
You must use the EFS mount helper to mount your Amazon EFS file systems in order to use IAM authorization to control client access\. For more information, see [Mounting with IAM authorization](efs-mount-helper.md#mounting-IAM-option)\.
- **Important**  
 If you grant permission to an individual IAM user or role in a file system policy, don't delete or recreate that user or role while the policy is in effect on the file system\. If this happens, that user or role is effectively locked out from file system and will not be able to access it\. For more information, see [Specifying a Principal](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html#Principal_specifying) in the *IAM User Guide*\.


## NFS-Level users, groups, and permissions

- **Note**  
When you create a user on an EC2 instance, you can assign any numeric user ID \(UID\) and group ID \(GID\) to the user\. The numeric user IDs are set in the `/etc/passwd` file on Linux systems\. The numeric group IDs are in the `/etc/group` file\. These files define the mappings between names and IDs\. Outside of the EC2 instance, Amazon EFS doesn't perform any authentication of these IDs, including the root ID of 0\.


## Working with access points

- **Important**  
Enforcing a user identity is subject to the `ClientRootAccess` IAM permission\.   
For example, in some cases you might configure the access point user ID, group ID, or both to be root \(that is, setting the UID, GID, or both to 0\)\. In such cases, you must grant the `ClientRootAccess` IAM permission to the NFS client\.


## Blocking public access

- **Note**  
Using Transfer Family with Amazon EFS is disabled by default for AWS accounts that have EFS file systems with policies that allow public access that were created before January 6, 2021\. To enable using Transfer Family to access your file system, contact AWS Support\.

