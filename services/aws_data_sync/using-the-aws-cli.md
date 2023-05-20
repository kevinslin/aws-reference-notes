---
id: Using the AWS CLI
title: Using the AWS CLI
created: 1683841041000
updated: 1683841041000
---
# Using the AWS CLI

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-datasync-user-guide.git)
{% endhint %}

## Creating an agent

- **Note**  
When you configure your agent to use Amazon VPC endpoints, the data transferred between your agent and the DataSync service doesn't cross the public internet and doesn't require public IP addresses\. For end\-to\-end instructions for this configuration, see [Using AWS DataSync in a virtual private cloud](datasync-in-vpc.md)\.
- **Note**  
The `.ova` default credentials are login **admin**, password **password**\. You can change the password on the virtual machine \(VM\) local console\. You don't need to log in to the VM for basic DataSync functionality\. Logging in is required mainly for troubleshooting, network\-specific settings, and so on\.  
You log in to the agent VM local console by using your VM's hypervisor client\. For information about how to use the VM local console, see [Working with your DataSync agent's local console](local-console-vm.md)\.
- **Note**  
After you choose a service endpoint, you can't change it later\.
- **Note**  
Make sure that you are using the same AWS credentials throughout the whole process\. Don't switch between multiple terminals where you are authenticated with different AWS credentials\.


## Creating locations

- **Note**  
If you are using an NFS location on an AWS Snowcone device, see [NFS server on AWS Snowcone](create-nfs-location.md#nfs-on-snowcone) for more information about transferring data to or from that device\.
- **Note**  
The AWS Region that you specify is the one where your target S3 bucket or EFS file system is located\.
- **Note**  
The AWS Region that you specify is the one where your target S3 bucket or EFS file system is located\.
- **Note**  
Changes to object data or metadata are equivalent to deleting an object and creating a new one to replace it\. This results in additional charges in the following scenarios:  
**When using object versioning** – Changes to object data or metadata create a new version of the object\.
**When using storage classes that can incur additional charges for overwriting, deleting, or retrieving, objects** – Changes to object data or metadata result in such charges\. For more information, see [Storage class considerations with Amazon S3 locations](create-s3-location.md#using-storage-classes)\. 
When you use object versioning, a single DataSync task execution might create more than one version of an Amazon S3 object\.
In addition to the IAM policies that grant DataSync permissions, we recommend creating a multipart upload bucket policy for your S3 buckets\. Doing this can help you control your storage costs\. For more information, see the blog post [ S3 lifecycle management update \- support for multipart uploads and delete markers](http://aws.amazon.com/blogs/aws/s3-lifecycle-management-update-support-for-multipart-uploads-and-delete-markers/)\.


## Starting a task

- **Note**  
Each agent can run a single task at a time\.

