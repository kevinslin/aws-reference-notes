---
id: MySQL on Amazon RDS
title: MySQL on Amazon RDS
created: 1683841041000
updated: 1683841041000
---
# MySQL on Amazon RDS

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## MySQL feature support

- **Note**  
The following lists are not exhaustive\.
- **Note**  
System tables in the `mysql` schema can be in MyISAM storage\.
- **Important**  
If your MySQL DB instance does not shut down normally, such as during a failover, then the buffer pool state will not be saved to disk\. In this case, MySQL loads whatever buffer pool file is available when the DB instance is restarted\. No harm is done, but the restored buffer pool might not reflect the most recent state of the buffer pool prior to the restart\. To ensure that you have a recent state of the buffer pool available to warm the InnoDB cache on startup, we recommend that you periodically dump the buffer pool "on demand\."  
You can create an event to dump the buffer pool automatically and on a regular interval\. For example, the following statement creates an event named `periodic_buffer_pool_dump` that dumps the buffer pool every hour\.
- **Note**  
Global transaction IDs are supported for all RDS for MySQL 5\.7 versions, and for RDS for MySQL 8\.0\.26 and higher 8\.0 versions\.


## MySQL versions

- **Note**  
Dates with only a month and a year are approximate and are updated with an exact date when it’s known\.
- **Note**  
Dates with only a month and a year are approximate and are updated with an exact date when it’s known\.


## Connecting to a DB instance running MySQL

- **Note**  
For information on connecting to a MariaDB DB instance, see [Connecting to a DB instance running the MariaDB database engine](USER_ConnectToMariaDBInstance.md)\.
- **Important**  
Only use an unencrypted MySQL connection when the client and server are in the same VPC and the network is trusted\. For information about using encrypted connections, see [Connecting from the MySQL command\-line client with SSL/TLS \(encrypted\)](mysql-ssl-connections.md#USER_ConnectToInstanceSSL.CLI)\.


## Improving query performance with RDS Optimized Reads

- **Note**  
Both manual and automated RDS snapshots only contain engine files for persistent objects\. The temporary objects created in the instance store aren't included in RDS snapshots\.


## Upgrading the MySQL DB engine

- **Tip**  
You can minimize the downtime required for DB instance upgrade by using a blue/green deployment\. For more information, see [Using Amazon RDS Blue/Green Deployments for database updates](blue-green-deployments.md)\.
- **Note**  
Amazon RDS only takes DB snapshots if you have set the backup retention period for your DB instance to a number greater than 0\. To change your backup retention period, see [Modifying an Amazon RDS DB instance](Overview.DBInstance.Modifying.md)\.
- **Note**  
You can only create MySQL version 5\.7 and 8\.0 DB instances with latest\-generation and current\-generation DB instance classes, in addition to the db\.m3 previous\-generation DB instance class\.   
In some cases, you want to upgrade a MySQL version 5\.6 DB instance running on a previous\-generation DB instance class \(other than db\.m3\) to a MySQL version 5\.7 DB instance\. In these cases, first modify the DB instance to use a latest\-generation or current\-generation DB instance class\. After you do this, you can then modify the DB instance to use the MySQL version 5\.7 database engine\. For information on Amazon RDS DB instance classes, see [DB instance classes](Concepts.DBInstanceClass.md)\.
- **Note**  
Amazon RDS runs all of these prechecks only for an upgrade from MySQL 5\.7 to MySQL 8\.0\. For an upgrade from MySQL 5\.6 to MySQL 5\.7, prechecks are limited to confirming that there are no orphan tables and that there is enough storage space to rebuild tables\. Prechecks aren't run for upgrades to releases lower than MySQL 5\.7\.
- **Note**  
Currently, automatic rollback after upgrade failure is supported only for MySQL 5\.7 to 8\.0 major version upgrades\.
- **Note**  
When you are upgrading from MySQL version 5\.7 to MySQL version 8\.0, complete the prechecks before performing the upgrade\. For more information, see [Prechecks for upgrades from MySQL 5\.7 to 8\.0](#USER_UpgradeDBInstance.MySQL.57to80Prechecks)\.


## Importing data into a MySQL DB instance

- **Note**  
The `'mysql'` system database contains authentication and authorization information required to log in to your DB instance and access your data\. Dropping, altering, renaming, or truncating tables, data, or other contents of the `'mysql'` database in your DB instance can result in error and might render the DB instance and your data inaccessible\. If this occurs, you can restore the DB instance from a snapshot using the AWS CLI `restore-db-instance-from-db-snapshot` command\. You can recover the DB instance using the AWS CLI `restore-db-instance-to-point-in-time` command\.
- **Note**  
Using innodb\_flush\_log\_at\_trx\_commit=0 causes InnoDB to flush its logs every second instead of at each commit\. This provides a significant speed advantage, but can lead to data loss during a crash\. Use with caution\.


## Working with MySQL replication

- **Note**  
You can configure replication to import databases from a MariaDB or MySQL instance that is external to Amazon RDS, or to export databases to such instances\. For more information, see [Importing data to an Amazon RDS MariaDB or MySQL database with reduced downtime](MySQL.Procedural.Importing.NonRDSRepl.md) and [Exporting data from a MySQL DB instance by using replication](MySQL.Procedural.Exporting.NonRDSRepl.md)\.


## Common DBA tasks for MySQL

- **Note**  
First verify that the error in question can be safely skipped\. In a MySQL utility, connect to the read replica and run the following MySQL command\.
- **Important**  
If you attempt to call `mysql.rds_skip_repl_error` and encounter the following error: `ERROR 1305 (42000): PROCEDURE mysql.rds_skip_repl_error does not exist`, then upgrade your MySQL DB instance to the latest minor version or one of the minimum minor versions listed in [mysql\.rds\_skip\_repl\_error](mysql-stored-proc-replicating.md#mysql_rds_skip_repl_error)\.
- **Important**  
Setting a nondefault value for this parameter can lead to replication inconsistency\. Only set this parameter to a nondefault value if you have exhausted other options to resolve the problem and you are sure of the potential impact on your read replica's data\.


## Known issues and limitations

- **Note**  
Some existing DB instances have a lower limit\. For example, MySQL DB instances created before April 2014 have a file and table size limit of 2 TB\. This 2 TB file size limit also applies to DB instances or read replicas created from DB snapshots taken before April 2014, regardless of when the DB instance was created\.

