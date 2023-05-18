---
id: MariaDB on Amazon RDS
title: MariaDB on Amazon RDS
created: 1683841041000
updated: 1683841041000
---
# MariaDB on Amazon RDS

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## MariaDB feature support

- **Note**  
The following lists are not exhaustive\.
- **Important**  
If your MariaDB DB instance doesn't shut down normally, such as during a failover, then the buffer pool state isn't saved to disk\. In this case, MariaDB loads whatever buffer pool file is available when the DB instance is restarted\. No harm is done, but the restored buffer pool might not reflect the most recent state of the buffer pool before the restart\. To ensure that you have a recent state of the buffer pool available to warm the cache on startup, we recommend that you periodically dump the buffer pool "on demand\." You can dump or load the buffer pool on demand\.  
You can create an event to dump the buffer pool automatically and at a regular interval\. For example, the following statement creates an event named `periodic_buffer_pool_dump` that dumps the buffer pool every hour\.


## MariaDB versions

- **Note**  
Dates with only a month and a year are approximate and are updated with an exact date when it’s known\.
- **Note**  
Dates with only a month and a year are approximate and are updated with an exact date when it’s known\.


## Connecting to a DB instance running MariaDB

- **Important**  
Only use an unencrypted MySQL connection when the client and server are in the same VPC and the network is trusted\. For information about using encrypted connections, see [Connecting from the MySQL command\-line client with SSL/TLS \(encrypted\)](mariadb-ssl-connections.md#USER_ConnectToMariaDBInstanceSSL.CLI)\.


## Improving query performance with RDS Optimized Reads

- **Note**  
Both manual and automated RDS snapshots contain only the engine files for persistent objects\. The temporary objects created in the instance store aren't included in RDS snapshots\.


## Upgrading the MariaDB DB engine

- **Tip**  
You can minimize the downtime required for DB instance upgrade by using a blue/green deployment\. For more information, see [Using Amazon RDS Blue/Green Deployments for database updates](blue-green-deployments.md)\.
- **Note**  
Amazon RDS only takes DB snapshots if you have set the backup retention period for your DB instance to a number greater than 0\. To change your backup retention period, see [Modifying an Amazon RDS DB instance](Overview.DBInstance.Modifying.md)\.


## Importing data into a MariaDB DB instance

- **Note**  
The mysql system database contains authentication and authorization information required to log into your DB instance and access your data\. Dropping, altering, renaming, or truncating tables, data, or other contents of the mysql database in your DB instance can result in errors and might render the DB instance and your data inaccessible\. If this occurs, the DB instance can be restored from a snapshot using the AWS CLI [https://docs.aws.amazon.com/cli/latest/reference/rds/restore-db-instance-from-db-snapshot.html](https://docs.aws.amazon.com/cli/latest/reference/rds/restore-db-instance-from-db-snapshot.html) or recovered using [https://docs.aws.amazon.com/cli/latest/reference/rds/restore-db-instance-to-point-in-time.html](https://docs.aws.amazon.com/cli/latest/reference/rds/restore-db-instance-to-point-in-time.html) commands\.


## Options for MariaDB

- **Note**  
If you don't configure an option setting in the RDS console, RDS uses the default setting\.


## MariaDB limitations

- **Note**  
This list is not exhaustive\.

