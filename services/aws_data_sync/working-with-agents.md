---
id: Working with agents
title: Working with agents
created: 1683841041000
updated: 1683841041000
---
# Working with agents

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-datasync-user-guide.git)
{% endhint %}

## Creating an agent

- **Tip**  
You don't need an agent to copy data between AWS storage services\.


## Deploying your agent in an AWS Region

- **Important**  
Deploy your agent such that it doesn't require network traffic between Availability Zones \(to avoid charges for such traffic\)\.   
To access your Amazon EFS or FSx for Windows File Server file system, deploy the agent in an Availability Zone that has a mount target to your file system\.
For self\-managed file systems, deploy the agent in the Availability Zone where your file system resides\.
To learn more about data transfer prices for all AWS Regions, see [Amazon EC2 On\-Demand pricing](http://aws.amazon.com/ec2/pricing/on-demand/)\.
- **Note**  
Deploy the agent in the AWS Region and AWS account where the source file system resides\.  
When you're copying between two Amazon EFS file systems in different AWS accounts, we recommend that you use the NFS \(source\) to EFS \(destination\) transfer\.
When you're copying between two Amazon FSx file systems in different AWS accounts, we recommend that you use the Server Message Block \(SMB\) \(source\) to Amazon FSx \(destination\) transfer\.


## Working with your agent's local console

- **Tip**  
You don't need to use the agent's local console for standard DataSync functionality\.
- **Note**  
If you add a new rule to an existing security group, the new rule applies to all instances that use that security group\. For more information about security groups and how to add a security group rule, see [Amazon EC2 security groups for Linux instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html) in the *Amazon EC2 User Guide for Linux Instances\.*


## Deleting an agent

- **Note**  
Deleting doesn't remove the agent's virtual machine \(VM\) from your environment\. You can reuse the VM to create and activate a new agent\.

