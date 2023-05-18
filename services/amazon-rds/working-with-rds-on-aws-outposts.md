---
id: Working with RDS on AWS Outposts
title: Working with RDS on AWS Outposts
created: 1683841041000
updated: 1683841041000
---
# Working with RDS on AWS Outposts

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Customer-owned IP addresses

- **Note**  
In some cases, you might turn on CoIPs for a DB instance but Amazon RDS isn't able to allocate a CoIP for the DB instance\. In such cases, the DB instance status is changed to **incompatible\-network**\. For more information about the DB instance status, see [Viewing Amazon RDS DB instance status](accessing-monitoring.md#Overview.DBInstance.Status)\.


## Creating DB instances for RDS on Outposts

- **Note**  
To create a DB subnet group for the AWS Cloud, specify at least two subnets\.

