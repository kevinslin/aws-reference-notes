---
id: What is Aurora?
title: What is Aurora?
created: 1683841041000
updated: 1683841041000
---
# What is Aurora?

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Aurora DB clusters

- **Note**  
The preceding information applies to provisioned clusters, parallel query clusters, global database clusters, Aurora Serverless clusters, and all MySQL 8\.0\-compatible, 5\.7\-compatible, and PostgreSQL\-compatible clusters\.


## Aurora versions

- **Note**  
If you want to remain on an LTS minor version for the duration of its lifecycle, make sure to turn off **Auto minor version upgrade** for your DB instances\. To avoid automatically upgrading your DB cluster from the LTS minor version, set **Auto minor version upgrade** to `No` on any DB instance in your Aurora cluster\.


## Regions and Availability Zones

- **Note**  
For information about finding the Availability Zones for an AWS Region, see [Describe your Availability Zones](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html#availability-zones-describe) in the Amazon EC2 documentation\.
- **Note**  
Aurora doesn't support Local Zones\.


## Aurora connection management

- **Tip**  
 Through RDS Proxy, you can create additional read\-only endpoints for an Aurora cluster\. These endpoints perform the same kind of load\-balancing as the Aurora reader endpoint\. Applications can reconnect more quickly to the proxy endpoints than the Aurora reader endpoint if reader instances become unavailable\. The proxy endpoints can also take advantage of other proxy features such as multiplexing\. For more information, see [Using reader endpoints with Aurora clusters](rds-proxy-endpoints.md#rds-proxy-endpoints-reader)\.
- **Note**  
 You must also create and manage custom endpoints for Aurora clusters restored from snapshots\. Custom endpoints are not included in the snapshot\. You create them again after restoring, and choose new endpoint names if the restored cluster is in the same region as the original one\.


## DB instance classes

- **Note**  
We recommend using the T DB instance classes only for development, test, or other nonproduction servers\. For more detailed recommendations for the T instance classes, see [Using T instance classes for development and testing](AuroraMySQL.BestPractices.md#AuroraMySQL.BestPractices.T2Medium)\.
- **Note**  
When you perform operations with the AWS CLI, it automatically shows the supported DB instance classes for a specific DB engine, DB engine version, and AWS Region\. Examples of the operations that you can perform include creating and modifying a DB instance\.


## Aurora storage and reliability

- **Note**  
The storage limits and dynamic resizing behavior discussed here apply to persistent tables and other data stored in the cluster volume\.   
For Aurora PostgreSQL, temporary table data is stored in the local DB instance\.  
For Aurora MySQL version 2, temporary table data is stored by default in the cluster volume for writer instances and in local storage for reader instances\. For more information, see [Storage engine for on\-disk temporary tables](AuroraMySQL.CompareMySQL57.md#AuroraMySQL.StorageEngine57)\.  
For Aurora MySQL version 3, temporary table data is stored in the local DB instance or in the cluster volume\. For more information, see [New temporary table behavior in Aurora MySQL version 3](ams3-temptable-behavior.md)\.  
The maximum size of temporary tables that reside in local storage is limited by the maximum local storage size of the DB instance\. The local storage size depends on the instance class that you use\. For more information, see [Temporary storage limits for Aurora MySQLTemporary storage limits](AuroraMySQL.Managing.Performance.md#AuroraMySQL.Managing.TempStorage) and [Temporary storage limits for Aurora PostgreSQLTemporary storage limits](AuroraPostgreSQL.Managing.md#AuroraPostgreSQL.Managing.TempStorage)\.
- **Tip**  
For earlier versions without the dynamic resizing feature, resetting the storage usage for a cluster involved doing a logical dump and restoring to a new cluster\. That operation can take a long time for a substantial volume of data\. If you encounter this situation, consider upgrading your cluster to a version that supports dynamic volume resizing\.


## High availability for Amazon Aurora

- **Tip**  
Within each AWS Region, Availability Zones \(AZs\) represent locations that are distinct from each other to provide isolation in case of outages\. We recommend that you distribute the primary instance and reader instances in your DB cluster over multiple Availability Zones to improve the availability of your DB cluster\. That way, an issue that affects an entire Availability Zone doesn't cause an outage for your cluster\.   
You can set up a Multi\-AZ cluster by making a simple choice when you create the cluster\. The choice is simple whether you use the AWS Management Console, the AWS CLI, or the Amazon RDS API\. You can also make an existing Aurora cluster into a Multi\-AZ cluster by adding a new reader instance and specifying a different Availability Zone\.
- **Tip**  
 In Aurora MySQL 2\.10 and higher, you can improve availability during a failover by having more than one reader DB instance in a cluster\. In Aurora MySQL 2\.10 and higher, Aurora restarts only the writer DB instance and the failover target during a failover\. Other reader DB instances in the cluster remain available to continue processing queries through connections to the reader endpoint\.   
You can also improve availability during a failover by using RDS Proxy with your Aurora DB cluster\. For more information, see [High availability with Amazon RDS Proxy](#Concepts.AuroraHighAvailability.Proxy)\.
- **Note**  
Amazon Aurora also supports replication with an external MySQL database, or an RDS MySQL DB instance\. For more information, see [Replication between Aurora and MySQL or between Aurora and another Aurora DB cluster \(binary log replication\)](AuroraMySQL.Replication.MySQL.md)\.


## Replication with Aurora

- **Tip**  
 You can use Aurora Replicas within an Aurora cluster as your only form of replication to keep your data highly available\. You can also combine the built\-in Aurora replication with the other types of replication\. Doing so can help to provide an extra level of high availability and geographic distribution of your data\.

