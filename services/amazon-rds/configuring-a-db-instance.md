---
id: Configuring a DB instance
title: Configuring a DB instance
created: 1683841041000
updated: 1683841041000
---
# Configuring a DB instance

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Creating a DB instance

- **Important**  
Before you can create an Amazon RDS DB instance, you must complete the tasks in [Setting up for Amazon RDS](CHAP_SettingUp.md)\.
- **Note**  
In the following procedure, **Standard create** is enabled, and **Easy create** isn't enabled\. This procedure uses Microsoft SQL Server as an example\.  
For examples that use **Easy create** to walk you through creating and connecting to sample DB instances for each engine, see [Getting started with Amazon RDS](CHAP_GettingStarted.md)\.


## Working with option groups

- **Note**  
Currently, you can't copy an option group to a different AWS Region\.
- **Note**  
If you specify a security group as a value for an option in an option group, manage the security group by modifying the option group\. You can't change or remove this security group by modifying a DB instance\. Also, the security group doesn't appear in the DB instance details in the AWS Management Console or in the output for the AWS CLI command `describe-db-instances`\.
- **Note**  
If you specify a security group as a value for an option in an option group, you manage the security group by modifying the option group\. You can't change or remove this security group by modifying a DB instance\. Also, the security group doesn't appear in the DB instance details in the AWS Management Console or in the output for the AWS CLI command `describe-db-instances`\.
- **Note**  
You can't modify the option group of an automated DB snapshot\.


## Working with parameter groups

- **Note**  
Some DB engines offer additional features that you can add to your database as options in an option group\. For information about option groups, see [Working with option groups](USER_WorkingWithOptionGroups.md)\.

