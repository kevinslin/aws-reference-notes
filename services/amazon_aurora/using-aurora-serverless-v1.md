---
id: Using Aurora Serverless v1
title: Using Aurora Serverless v1
created: 1683841041000
updated: 1683841041000
---
# Using Aurora Serverless v1

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## How Aurora Serverless v1 works

- **Note**  
 If a DB cluster is paused for more than seven days, the DB cluster might be backed up with a snapshot\. In this case, Aurora restores the DB cluster from the snapshot when there is a request to connect to it\.
- **Note**  
The `max_connections` value doesn't scale linearly with the number of ACUs\.


## Creating an Aurora Serverless v1 DB cluster

- **Note**  
 The cluster volume for an Aurora Serverless v1 cluster is always encrypted\. When you create your Aurora Serverless v1 DB cluster, you can't turn off encryption, but you can choose to use your own encryption key\. With Aurora Serverless v2, you can choose whether to encrypt the cluster volume\.
- **Note**  
If you receive the following error message when trying to create your cluster, your account needs additional permissions\.   
`Unable to create the resource. Verify that you have permission to create service linked role. Otherwise wait and try again later.`  
See [Using service\-linked roles for Amazon Aurora](UsingWithRDS.IAM.ServiceLinkedRoles.md) for more information\.


## Restoring an Aurora Serverless v1 DB cluster

- **Note**  
 If you encounter the following error message, your account requires additional permissions:   
 `Unable to create the resource. Verify that you have permission to create service linked role. Otherwise wait and try again later.`   
 For more information, see [Using service\-linked roles for Amazon Aurora](UsingWithRDS.IAM.ServiceLinkedRoles.md)\.
- **Note**  
The version of the DB cluster snapshot must be compatible with Aurora Serverless v1\. For the list of supported versions, see [Aurora Serverless v1](Concepts.Aurora_Fea_Regions_DB-eng.Feature.ServerlessV1.md)\.


## Modifying an Aurora Serverless v1 DB cluster

- **Note**  
Aurora PostgreSQL version 10 is deprecated\. Upgrade your PostgreSQL 10–compatible Aurora Serverless v1 DB clusters to PostgreSQL 11–compatible ones before converting them\.  
Aurora MySQL version 1 is deprecated\. Upgrade your MySQL 5\.6–compatible Aurora Serverless v1 DB clusters to MySQL 5\.7–compatible ones before converting them\.  
For more information, see [Upgrading the major version of an Aurora Serverless v1 DB cluster](#aurora-serverless.modifying.upgrade)\.
- **Note**  
Depending on the DB instance class you choose, and your database usage, you might see different costs for a provisioned DB cluster compared to Aurora Serverless v1\.  
If you convert your Aurora Serverless v1 DB cluster to a burstable \(db\.t\*\) DB instance class, you might incur additional costs for using the DB cluster\. For more information, see [DB instance class types](Concepts.DBInstanceClass.md#Concepts.DBInstanceClass.Types)\.


## Viewing Aurora Serverless v1 DB clusters

- **Note**  
 You can't connect directly to specific DB instances in your Aurora Serverless v1 DB clusters\.

