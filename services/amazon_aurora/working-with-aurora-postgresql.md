---
id: Working with Aurora PostgreSQL
title: Working with Aurora PostgreSQL
created: 1683841041000
updated: 1683841041000
---
# Working with Aurora PostgreSQL

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Updating applications for new SSL/TLS certificates

- **Note**  
Some applications are configured to connect to Aurora PostgreSQL DB clusters only if they can successfully verify the certificate on the server\.   
For such applications, you must update your client application trust stores to include the new CA certificates\.
- **Note**  
When you update the trust store, you can retain older certificates in addition to adding the new certificates\.
- **Important**  
After you have determined that your database connections use SSL/TLS and have updated your application trust store, you can update your database to use the rds\-ca\-2019 certificates\. For instructions, see step 3 in [Updating your CA certificate by modifying your DB instance](UsingWithRDS.SSL-certificate-rotation.md#UsingWithRDS.SSL-certificate-rotation-updating)\.


## Migrating data to Aurora PostgreSQL

- **Important**  
If you plan to migrate an RDS for PostgreSQL DB instance to an Aurora PostgreSQL DB cluster in the near future, we strongly recommend that you turn off auto minor version upgrades for the DB instance early in the migration planning phase\. Migration to Aurora PostgreSQL might be delayed if the RDS for PostgreSQL version isn't yet supported by Aurora PostgreSQL\.   
For information about Aurora PostgreSQL versions, see [ Engine versions for Amazon Aurora PostgreSQL](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraPostgreSQL.Updates.20180305.html)\.
- **Note**  
It can take several hours per terabyte of data for the migration to complete\.


## Using Babelfish for Aurora PostgreSQL

- **Note**  
Babelfish for Aurora PostgreSQL supports TDS versions 7\.1 through 7\.4\.


## Managing Aurora PostgreSQL

- **Note**  
We recommend using the T DB instance classes only for development and test servers, or other non\-production servers\. For more details on the T instance classes, see [DB instance class types](Concepts.DBInstanceClass.md#Concepts.DBInstanceClass.Types)\.
- **Tip**  
If your applications frequently open and close connections, or keep a large number of long\-lived connections open, we recommend that you use Amazon RDS Proxy\. RDS Proxy is a fully managed, highly available database proxy that uses connection pooling to share database connections securely and efficiently\. To learn more about RDS Proxy, see [Using Amazon RDS Proxy for Aurora](rds-proxy.md)\.


## Tuning with wait events for Aurora PostgreSQL

- **Important**  
The wait events in this section are specific to Aurora PostgreSQL\. Use the information in this section to tune Amazon Aurora only, not RDS for PostgreSQL\.  
Some wait events in this section have no analogs in the open source versions of these database engines\. Other wait events have the same names as events in open source engines, but behave differently\. For example, Amazon Aurora storage works differently from open source storage, so storage\-related wait events indicate different resource conditions\.


## Replication with Aurora PostgreSQL

- **Note**  
Rebooting the writer DB instance of an Amazon Aurora DB cluster also automatically reboots the Aurora Replicas for that DB cluster\. The automatic reboot re\-establishes an entry point that guarantees read/write consistency across the DB cluster\.


## Working with extensions and foreign data wrappers

- **Note**  
As of Aurora PostgreSQL 14\.5, Aurora PostgreSQL supports Trusted Language Extensions for PostgreSQL\. This feature is implemented as the extension `pg_tle`, which you can add to your Aurora PostgreSQL\. By using this extension, developers can create their own PostgreSQL extensions in a safe environment that simplifies the setup and configuration requirements, as well as much of the preliminary testing for new extensions\. For more information, see [Working with Trusted Language Extensions for PostgreSQL](PostgreSQL_trusted_language_extension.md)\.
- **Note**  
Parameter settings at the session level take precedence over the settings in the custom DB cluster parameter group for the Aurora PostgreSQL DB cluster's writer instance\. If you don't want database users to bypass your audit logging configuration settings, be sure to change their permissions\.


## Working with Trusted Language Extensions for PostgreSQL

- **Note**  
You need to have the privileges of the `pgtle_admin` role to follow this procedure\.

