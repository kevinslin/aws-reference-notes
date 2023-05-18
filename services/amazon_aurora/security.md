---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Database authentication

- **Important**  
We strongly recommend that you do not use the master user directly in your applications\. Instead, adhere to the best practice of using a database user created with the minimal privileges required for your application\.


## Password management with Aurora and Secrets Manager

- **Note**  
This policy enforces password management in AWS Secrets Manager at creation\. However, you can still disable Secrets Manager integration and manually set a master password by modifying the cluster\.  
To prevent this, include `rds:ModifyDBInstance`, `rds:ModifyDBCluster` in the Action block of the policy\. Be aware, this prevents the user from applying any further modifications to existing clusters which do not have Secrets Manager integration enabled\.


## Infrastructure security

- **Note**  
If your DB instance is in a VPC but isn't publicly accessible, you can also use an AWS Site\-to\-Site VPN connection or an AWS Direct Connect connection to access it from a private network\. For more information, see [Internetwork traffic privacy](inter-network-traffic-privacy.md)\.


## Controlling access with security groups

- **Note**  
In an Aurora DB cluster, the VPC security group associated with the DB cluster is also associated with all of the DB instances in the DB cluster\. If you change the VPC security group for the DB cluster or for a DB instance, the change is applied automatically to all of the DB instances in the DB cluster\.
- **Note**  
If your DB cluster is in a VPC but isn't publicly accessible, you can also use an AWS Site\-to\-Site VPN connection or an AWS Direct Connect connection to access it from a private network\. For more information, see [Internetwork traffic privacy](inter-network-traffic-privacy.md)\.


## Master user account privileges

- **Important**  
We strongly recommend that you do not use the master user directly in your applications\. Instead, adhere to the best practice of using a database user created with the minimal privileges required for your application\.
- **Note**  
If you accidentally delete the permissions for the master user, you can restore them by modifying the DB cluster and setting a new master user password\. For more information about modifying a DB cluster, see [Modifying an Amazon Aurora DB cluster](Aurora.Modifying.md)\.


## Service-linked roles

- **Note**  
You must configure permissions to allow an IAM entity \(such as a user, group, or role\) to create, edit, or delete a service\-linked role\. If you encounter the following error message:  
**Unable to create the resource\. Verify that you have permission to create service linked role\. Otherwise wait and try again later\.**  
 Make sure you have the following permissions enabled:
- **Important**  
If you were using the Amazon Aurora service before December 1, 2017, when it began supporting service\-linked roles, then Amazon Aurora created the AWSServiceRoleForRDS role in your account\. To learn more, see [A new role appeared in my AWS account](https://docs.aws.amazon.com/IAM/latest/UserGuide/troubleshoot_roles.html#troubleshoot_roles_new-role-appeared)\.

