---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Database authentication

- **Important**  
We strongly recommend that you do not use the master user directly in your applications\. Instead, adhere to the best practice of using a database user created with the minimal privileges required for your application\.
- **Note**  
Currently, Kerberos authentication isn't supported for MariaDB DB instances\.


## Password management with RDS and Secrets Manager

- **Note**  
This policy enforces password management in AWS Secrets Manager at creation\. However, you can still disable Secrets Manager integration and manually set a master password by modifying the instance\.  
To prevent this, include `rds:ModifyDBInstance`, `rds:ModifyDBCluster` in the Action block of the policy\. Be aware, this prevents the user from applying any further modifications to existing instances which do not have Secrets Manager integration enabled\.


## Infrastructure security

- **Note**  
If your DB instance is in a VPC but isn't publicly accessible, you can also use an AWS Site\-to\-Site VPN connection or an AWS Direct Connect connection to access it from a private network\. For more information, see [Internetwork traffic privacy](inter-network-traffic-privacy.md)\.


## Controlling access with security groups

- **Note**  
If your DB instance is in a VPC but isn't publicly accessible, you can also use an AWS Site\-to\-Site VPN connection or an AWS Direct Connect connection to access it from a private network\. For more information, see [Internetwork traffic privacy](inter-network-traffic-privacy.md)\.
- **Note**  
The RDS console displays different security group rule names for your database if the Port value is configured to a non\-default value\.


## Master user account privileges

- **Important**  
We strongly recommend that you do not use the master user directly in your applications\. Instead, adhere to the best practice of using a database user created with the minimal privileges required for your application\.
- **Note**  
If you accidentally delete the permissions for the master user, you can restore them by modifying the DB instance and setting a new master user password\. For more information about modifying a DB instance, see [Modifying an Amazon RDS DB instance](Overview.DBInstance.Modifying.md)\.


## Service-linked roles

- **Note**  
You must configure permissions to allow an IAM entity \(such as a user, group, or role\) to create, edit, or delete a service\-linked role\. If you encounter the following error message:  
**Unable to create the resource\. Verify that you have permission to create service linked role\. Otherwise wait and try again later\.**  
 Make sure you have the following permissions enabled:
- **Important**  
If you were using the Amazon RDS service before December 1, 2017, when it began supporting service\-linked roles, then Amazon RDS created the AWSServiceRoleForRDS role in your account\. To learn more, see [A new role appeared in my AWS account](https://docs.aws.amazon.com/IAM/latest/UserGuide/troubleshoot_roles.html#troubleshoot_roles_new-role-appeared)\.
- **Note**  
You must configure permissions to allow an IAM entity \(such as a user, group, or role\) to create, edit, or delete a service\-linked role\. If you encounter the following error message:  
**Unable to create the resource\. Verify that you have permission to create service linked role\. Otherwise wait and try again later\.**  
 Make sure you have the following permissions enabled:

