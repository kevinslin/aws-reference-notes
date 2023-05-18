---
id: PostgreSQL on Amazon RDS
title: PostgreSQL on Amazon RDS
created: 1683841041000
updated: 1683841041000
---
# PostgreSQL on Amazon RDS

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## PostgreSQL features

- **Note**  
Huge pages aren't supported for db\.m1, db\.m2, and db\.m3 DB instance classes\.
- **Note**  
In addition to the native PostgreSQL logical replication feature introduced in PostgreSQL 10, RDS for PostgreSQL also supports the `pglogical` extension\. For more information, see [Using pglogical to synchronize data across instances](Appendix.PostgreSQL.CommonDBATasks.Extensions.md#Appendix.PostgreSQL.CommonDBATasks.pglogical)\.


## Connecting to a PostgreSQL instance

- **Note**  
A connection attempt with `--no-password` fails when the server requires password authentication and a password is not available from other sources\. For more information, see the [psql documentation](https://www.postgresql.org/docs/13/app-psql.html)\.


## Using a custom DNS server for outbound network access

- **Note**  
If you don't set up a custom DNS server and `rds.custom_dns_resolution` is set to 1, hosts are resolved using an Amazon Route 53 private zone\. For more information, see [Working with private hosted zones](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/hosted-zones-private.html)\.


## Upgrading the PostgreSQL DB engine

- **Note**  
Amazon RDS takes DB snapshots during the upgrade process only if you have set the backup retention period for your DB instance to a number greater than 0\. To change your backup retention period, see [Modifying an Amazon RDS DB instance](Overview.DBInstance.Modifying.md)\.
- **Note**  
A PostgreSQL upgrade doesn't upgrade PostgreSQL extensions\. To upgrade extensions, see [Upgrading PostgreSQL extensions](#USER_UpgradeDBInstance.PostgreSQL.ExtensionUpgrades)\.
- **Note**  
For information about updating the PostGIS extension, see [Managing spatial data with the PostGIS extension](Appendix.PostgreSQL.CommonDBATasks.PostGIS.md) \([Step 6: Upgrade the PostGIS extension](Appendix.PostgreSQL.CommonDBATasks.PostGIS.md#Appendix.PostgreSQL.CommonDBATasks.PostGIS.Update)\)\.  
To update the `pg_repack` extension, drop the extension and then create the new version in the upgraded DB instance\. For more information, see [pg\_repack installation](https://reorg.github.io/pg_repack/) in the `pg_repack` documentation\.


## Upgrading a PostgreSQL DB snapshot engine version

- **Note**  
You can't upgrade automated DB snapshots that are created during the automated backup process\.


## Working with read replicas for RDS for PostgreSQL

- **Note**  
For cascading read replicas, RDS for PostgreSQL supports 15 read replicas for each source DB instance at first level of replication, and 5 read replicas for each source DB instance at the second and third level of replication\.


## Importing data into PostgreSQL

- **Note**  
The PostgreSQL command `pg_dumpall` requires super\_user permissions that are not granted when you create a DB instance, so it cannot be used for importing data\.


## Exporting PostgreSQL data to Amazon S3

- **Note**  
Cross\-account export to Amazon S3 isn't supported\.
- **Note**  
You can save DB snapshot data to Amazon S3 using the AWS Management Console, AWS CLI, or Amazon RDS API\. For more information, see [Exporting DB snapshot data to Amazon S3](USER_ExportSnapshot.md)\.


## Invoking a Lambda function from RDS for PostgreSQL

- **Note**  
Invoking an AWS Lambda function is supported in these RDS for PostgreSQL versions:  
All PostgreSQL 15 versions
PostgreSQL 14\.1 and higher minor versions
PostgreSQL 13\.2 and higher minor versions
PostgreSQL 12\.6 and higher minor versions


## Using PostgreSQL extensions

- **Note**  
As of RDS for PostgreSQL 14\.5, RDS for PostgreSQL supports Trusted Language Extensions for PostgreSQL\. This feature is implemented as the extension `pg_tle`, which you can add to your RDS for PostgreSQL DB instance\. By using this extension, developers can create their own PostgreSQL extensions in a safe environment that simplifies the setup and configuration requirements\. For more information, see [Working with Trusted Language Extensions for PostgreSQL](PostgreSQL_trusted_language_extension.md)\.
- **Note**  
RDS for PostgreSQL doesn't support the `utl_file` package that is part of the orafce extension\. This is because the `utl_file` schema functions provide read and write operations on operating\-system text files, which requires superuser access to the underlying host\. As a managed service, RDS for PostgreSQL doesn't provide host access\.
- **Note**  
Parameter settings at the session level take precedence over the settings in the custom DB parameter group for the RDS for PostgreSQL DB instance\. If you don't want database users to bypass your audit logging configuration settings, be sure to change their permissions\.


## Working with Trusted Language Extensions for PostgreSQL

- **Note**  
You need to have the privileges of the `pgtle_admin` role to follow this procedure\.

