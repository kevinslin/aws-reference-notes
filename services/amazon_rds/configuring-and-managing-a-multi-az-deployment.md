---
id: Configuring and managing a Multi-AZ deployment
title: Configuring and managing a Multi-AZ deployment
created: 1683841041000
updated: 1683841041000
---
# Configuring and managing a Multi-AZ deployment

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Multi-AZ DB instance deployments

- **Note**  
The high availability option isn't a scaling solution for read\-only scenarios\. You can't use a standby replica to serve read traffic\. To serve read\-only traffic, use a Multi\-AZ DB cluster or a read replica instead\. For more information about Multi\-AZ DB clusters, see [Multi\-AZ DB cluster deployments](multi-az-db-clusters-concepts.md)\. For more information about read replicas, see [Working with DB instance read replicas](USER_ReadRepl.md)\.
- **Important**  
Using a snapshot to create the standby instance avoids downtime when you convert from Single\-AZ to Multi\-AZ, but you can experience a performance impact during and after converting to Multi\-AZ\. This impact can be significant for workloads that are sensitive to write latency\.  
While this capability lets large volumes be restored from snapshots quickly, it can cause a significant increase in the latency of I/O operations because of the synchronous replication\. This latency can impact your database performance\. We highly recommend as a best practice not to perform Multi\-AZ conversion on a production DB instance\.  
To avoid the performance impact on the DB instance currently serving the sensitive workload, create a read replica and enable backups on the read replica\. Convert the read replica to Multi\-AZ, and run queries that load the data into the read replica's volumes \(on both AZs\)\. Then promote the read replica to be the primary DB instance\. For more information, see [Working with DB instance read replicas](USER_ReadRepl.md)\.
- **Note**  
You can force a failover manually when you reboot a DB instance\. For more information, see [Rebooting a DB instance](USER_RebootInstance.md)\.
- **Note**  
The default TTL can vary according to the version of your JVM and whether a security manager is installed\. Many JVMs provide a default TTL less than 60 seconds\. If you're using such a JVM and not using a security manager, you can ignore the rest of this topic\. For more information on security managers in Oracle, see [The security manager](https://docs.oracle.com/javase/tutorial/essential/environment/security.html) in the Oracle documentation\.


## Multi-AZ DB cluster deployments

- **Important**  
Multi\-AZ DB clusters aren't the same as Aurora DB clusters\. For information about Aurora DB clusters, see the [Amazon Aurora User Guide](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html)\.
- **Important**  
To prevent replication errors in RDS for MySQL Multi\-AZ DB clusters, we strongly recommend that all tables have a primary key\.
- **Note**  
The delay is shown in microseconds\.
- **Note**  
The default TTL can vary according to the version of your JVM and whether a security manager is installed\. Many JVMs provide a default TTL less than 60 seconds\. If you're using such a JVM and not using a security manager, you can ignore the rest of this topic\. For more information on security managers in Oracle, see [The security manager](https://docs.oracle.com/javase/tutorial/essential/environment/security.html) in the Oracle documentation\.

