---
id: Working with Aurora MySQL
title: Working with Aurora MySQL
created: 1683841041000
updated: 1683841041000
---
# Working with Aurora MySQL

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Security with Aurora MySQL

- **Note**  
For more information, see [Security in Amazon Aurora](UsingWithRDS.md)\.
- **Important**  
We strongly recommend that you do not use the master user directly in your applications\. Instead, adhere to the best practice of using a database user created with the minimal privileges required for your application\.
- **Note**  
Encryption of a database instance and snapshots is not supported for the China \(Ningxia\) region\.
- **Note**  
The `require_secure_transport` parameter is available for Aurora MySQL version 2 and 3\. You can set this parameter in a custom DB cluster parameter group\. The parameter isn't available in DB instance parameter groups\.
- **Note**  
For more information on SSL/TLS connections with MySQL, see the [MySQL documentation](https://dev.mysql.com/doc/refman/5.7/en/using-encrypted-connections.html)\.
- **Note**  
`DHE-RSA` ciphers are only supported by Aurora MySQL versions before 2\.11\.0\. Versions 2\.11\.0 and higher support only `ECDHE` ciphers\.


## Updating applications for new SSL/TLS certificates

- **Note**  
Some applications are configured to connect to Aurora MySQL DB clusters only if they can successfully verify the certificate on the server\.   
For such applications, you must update your client application trust stores to include the new CA certificates\.
- **Note**  
If you use either the MySQL Java Connector v5\.1\.38 or later, or the MySQL Java Connector v8\.0\.9 or later to connect to your databases, even if you haven't explicitly configured your applications to use SSL/TLS when connecting to your databases, these client drivers default to using SSL/TLS\. In addition, when using SSL/TLS, they perform partial certificate verification and fail to connect if the database server certificate is expired\.
- **Note**  
When you update the trust store, you can retain older certificates in addition to adding the new certificates\.
- **Important**  
After you have determined that your database connections use SSL/TLS and have updated your application trust store, you can update your database to use the rds\-ca\-2019 certificates\. For instructions, see step 3 in [Updating your CA certificate by modifying your DB instance](UsingWithRDS.SSL-certificate-rotation.md#UsingWithRDS.SSL-certificate-rotation-updating)\.


## Migrating data to Aurora MySQL

- **Note**  
If you are migrating a MySQL database external to Amazon RDS, the migration options described in the table are supported only if your database supports the InnoDB or MyISAM tablespaces\.
If the MySQL database you are migrating to Aurora MySQL uses `memcached`, remove `memcached` before migrating it\.


## Tuning Aurora MySQL

- **Important**  
The wait events and thread states in this section are specific to Aurora MySQL\. Use the information in this section to tune only Amazon Aurora, not Amazon RDS for MySQL\.  
Some wait events in this section have no analogs in the open source versions of these database engines\. Other wait events have the same names as events in open source engines, but behave differently\. For example, Amazon Aurora storage works different from open source storage, so storage\-related wait events indicate different resource conditions\.


## Parallel query for Aurora MySQL

- **Tip**  
The PostgreSQL database engine also has a feature called "parallel query\." That feature is unrelated to Aurora parallel query\.
- **Note**  
 The parallel query optimization provides the most benefit for long\-running queries that take minutes or hours to complete\. Aurora MySQL generally doesn't perform parallel query optimization for inexpensive queries\. It also generally doesn't perform parallel query optimization if another optimization technique makes more sense, such as query caching, buffer pool caching, or index lookups\. If you find that parallel query isn't being used when you expect it, see [Verifying which statements use parallel query](#aurora-mysql-parallel-query-verifying)\.
- **Note**  
 The architecture of Aurora MySQL parallel query differs from that of similarly named features in other database systems\. Aurora MySQL parallel query doesn't involve symmetric multiprocessing \(SMP\) and so doesn't depend on the CPU capacity of the database server\. The parallel processing happens in the storage layer, independent of the Aurora MySQL server that serves as the query coordinator\.
- **Note**  
 Because timings depend on many environmental factors, your results might be different\. Always conduct your own performance tests to confirm the findings with your own environment, workload, and so on\.
- **Tip**  
 When you view these examples in HTML, you can use the **Copy** widget in the upper\-right corner of each code listing to copy the SQL code to try yourself\. Using the **Copy** widget avoids copying the extra characters around the `mysql>` prompt and `->` continuation lines\.
- **Note**  
 Parallel query is typically used for the kinds of resource\-intensive queries that benefit from the hash join optimization\. The method for turning on the hash join optimization depends on the Aurora MySQL version\. For details for each version, see [Turning on hash join for parallel query clusters](#aurora-mysql-parallel-query-enabling-hash-join)\. For information about how to use hash joins effectively, see [Optimizing large Aurora MySQL join queries with hash joins](AuroraMySQL.BestPractices.md#Aurora.BestPractices.HashJoin)\.
- **Note**  
 Each `UNION` clause within the query is run sequentially\. Even if the query includes multiple stages that all use parallel query, it only runs a single parallel query at any one time\. Therefore, even a complex multistage query only counts as 1 toward the limit of concurrent parallel queries\.
- **Note**  
 Typically, after an `INSERT` statement, the data for the newly inserted rows is in the buffer pool\. Therefore, a table might not be eligible for parallel query immediately after inserting a large number of rows\. Later, after the data is evicted from the buffer pool during normal operation, queries against the table might begin using parallel query again\.
- **Note**  
 When conducting performance comparisons, the query cache can produce artificially low timing numbers\. Therefore, in benchmark\-like situations, you can use the `sql_no_cache` hint\. This hint prevents the result from being served from the query cache, even if the same query had been run previously\. The hint comes immediately after the `SELECT` statement in a query\. Many parallel query examples in this topic include this hint, to make query times comparable between versions of the query for which parallel query is turned on and turned off\.   
 Make sure that you remove this hint from your source when you move to production use of parallel query\.


## Advanced Auditing with Aurora MySQL

- **Tip**  
 For an Aurora DB cluster containing multiple DB instances, you might find it more convenient to examine the audit logs for all instances in the cluster\. To do so, you can use CloudWatch Logs\. You can turn on a setting at the cluster level to publish the Aurora MySQL audit log data to a log group in CloudWatch\. Then you can view, filter, and search the audit logs through the CloudWatch interface\. For more information, see [Publishing Amazon Aurora MySQL logs to Amazon CloudWatch Logs](AuroraMySQL.Integrating.CloudWatch.md)\.
- **Tip**  
Log file entries are not in sequential order\. To order the entries, use the timestamp value\. To see the latest events, you might have to review all log files\. For more flexibility in sorting and searching the log data, turn on the setting to upload the audit logs to CloudWatch and view them using the CloudWatch interface\.  
 To view audit data with more types of fields and with output in JSON format, you can also use the Database Activity Streams feature\. For more information, see [Monitoring Amazon Aurora with Database Activity Streams](DBActivityStreams.md)\.


## Replication with Aurora MySQL

- **Important**  
 Aurora Replicas for Aurora MySQL always use the `REPEATABLE READ` default transaction isolation level for operations on InnoDB tables\. You can use the `SET TRANSACTION ISOLATION LEVEL` command to change the transaction level only for the primary instance of an Aurora MySQL DB cluster\. This restriction avoids user\-level locks on Aurora Replicas, and allows Aurora Replicas to scale to support thousands of active user connections while still keeping replica lag to a minimum\.
- **Note**  
 DDL statements that run on the primary instance might interrupt database connections on the associated Aurora Replicas\. If an Aurora Replica connection is actively using a database object, such as a table, and that object is modified on the primary instance using a DDL statement, the Aurora Replica connection is interrupted\.
- **Note**  
 The China \(Ningxia\) Region does not support cross\-Region read replicas\.
- **Note**  
 Rebooting the primary instance of an Amazon Aurora DB cluster also automatically reboots the Aurora Replicas for that DB cluster, to re\-establish an entry point that guarantees read/write consistency across the DB cluster\.
- **Important**  
 The ZDR mechanism operates on a best\-effort basis\. The Aurora MySQL versions, instance classes, error conditions, compatible SQL operations, and other factors that determine where ZDR applies are subject to change at any time\.
- **Note**  
All data definition language \(DDL\) statements are replicated as statements, regardless of the `binlog_format` setting on the source DB instance\.
- **Note**  
You can't modify a default DB cluster parameter group\. If the read replica is using a default parameter group, create a new parameter group and associate it with the read replica\. For more information on DB cluster parameter groups, see [Working with parameter groups](USER_WorkingWithParamGroups.md)\.


## Best practices with Amazon Aurora MySQL

- **Tip**  
 If your database is sometimes idle but at other times has a substantial workload, you can use Aurora Serverless v2 as an alternative to T instances\. With Aurora Serverless v2, you define a capacity range and Aurora automatically scales your database up or down depending on the current workload\. For usage details, see [Using Aurora Serverless v2](aurora-serverless-v2.md)\. For the database engine versions that you can use with Aurora Serverless v2, see [Requirements for Aurora Serverless v2](aurora-serverless-v2.requirements.md)\.
- **Note**  
You can't compare data types in different categories\.
- **Note**  
For Aurora MySQL version 3, hash join support is available in all minor versions and is turned on by default\.  
For Aurora MySQL version 2, hash join support is available in all minor versions\. In Aurora MySQL version 2, the hash join feature is always controlled by the `aurora_disable_hash_join` value\.
- **Note**  
This setting overrides the decisions of the cost\-based optimizer\. While the setting can be useful for testing and development, we recommend that you not use it in production\.
- **Important**  
When you set up replication between a MySQL DB instance and an Amazon Aurora MySQL DB cluster, you should monitor the replication to ensure that it remains healthy and repair it if necessary\.
- **Note**  
You can't configure the `innodb_flush_log_at_trx_commit` parameter in Aurora MySQL version 3\. Aurora MySQL version 3 always uses the default setting of 1, which is ACID compliant\.
- **Note**  
While you can take precautions to reduce the possibility of deadlocks occurring, deadlocks are an expected database behavior and can still occur\. Applications should have the necessary logic to handle deadlocks when they are encountered\. For example, implement retry and backing\-off logic in the application\. It’s best to address the root cause of the issue but if a deadlock does occur, the application has the option to wait and retry\.

