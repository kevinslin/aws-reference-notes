---
id: Microsoft SQL Server on Amazon RDS
title: Microsoft SQL Server on Amazon RDS
created: 1683841041000
updated: 1683841041000
---
# Microsoft SQL Server on Amazon RDS

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Licensing SQL Server on Amazon RDS

- **Note**  
Licensing for SQL Server Web Edition supports only public and internet\-accessible webpages, websites, web applications, and web services\. This level of support is required for compliance with Microsoft's usage rights\. For more information, see [AWS service terms](http://aws.amazon.com/serviceterms)\.


## Updating applications for new SSL/TLS certificates

- **Note**  
Some applications are configured to connect to SQL Server DB instances only if they can successfully verify the certificate on the server\. ****  
For such applications, you must update your client application trust stores to include the new CA certificates\.
- **Note**  
If you use connectors other than the ones listed, see the specific connector's documentation for information about how it enforces encrypted connections\. For more information, see [Connection modules for Microsoft SQL databases](https://docs.microsoft.com/en-us/sql/connect/sql-connection-libraries?view=sql-server-ver15) in the Microsoft SQL Server documentation\.
- **Note**  
If `sqlcmd` is invoked with the `-C` option, it trusts the server certificate, even if that doesn't match the client\-side trust store\.
- **Note**  
If you use `TrustServerCertificate=true` \(or its equivalent\) in the connection string, the connection process skips the trust chain validation\. In this case, the application connects even if the certificate can't be verified\. Using `TrustServerCertificate=false` enforces certificate validation and is a best practice\.
- **Note**  
When you update the trust store, you can retain older certificates in addition to adding the new certificates\.


## Upgrading the SQL Server DB engine

- **Note**  
Amazon RDS only takes DB snapshots if you have set the backup retention period for your DB instance to a number greater than 0\. To change your backup retention period, see [Modifying an Amazon RDS DB instance](Overview.DBInstance.Modifying.md)\.
- **Important**  
If you have any snapshots that are encrypted using AWS KMS, we recommend that you initiate an upgrade before support ends\.


## Importing and exporting SQL Server databases

- **Note**  
Whether or not you use a KMS key, the native backup and restore tasks enable server\-side Advanced Encryption Standard \(AES\) 256\-bit encryption by default for files uploaded to S3\.
- **Note**  
You can't back up a database during the maintenance window, or while Amazon RDS is taking a snapshot\.
- **Note**  
For differential restores, either the database must be in the RESTORING state or a task must already exist that restores with NORECOVERY\.  
You can't restore later differential backups while the database is online\.  
You can't submit a restore task for a database that already has a pending restore task with RECOVERY\.  
Full restores with NORECOVERY and differential restores aren't supported on Multi\-AZ instances\.  
Restoring a database on a Multi\-AZ instance with read replicas is similar to restoring a database on a Multi\-AZ instance\. You don't have to take any additional actions to restore a database on a replica\.
- **Note**  
For log restores, either the database must be in a state of restoring or a task must already exist that restores with NORECOVERY\.  
You can't restore log backups while the database is online\.  
You can't submit a log restore task on a database that already has a pending restore task with RECOVERY\.  
Log restores aren't supported on Multi\-AZ instances\.
- **Note**  
To use this approach, the database must be in the RESTORING state without any pending restore tasks\.  
The `rds_finish_restore` procedure isn't supported on Multi\-AZ instances\.  
To finish restoring the database, use the master login\. Or use the user login that most recently restored the database or log with NORECOVERY\.
- **Note**  
You can't submit a DROP database request for a database that already has a pending restore or finish restore task\.  
To drop the database, use the master login\. Or use the user login that most recently restored the database or log with NORECOVERY\.
- **Note**  
You can't cancel a FINISH\_RESTORE task\.


## Multi-AZ for RDS for SQL Server

- **Note**  
If your DB instance is running Database Mirroring \(DBM\)—not Always On Availability Groups \(AGs\)—you might need to disable in\-memory optimization before you add Multi\-AZ\. Disable in\-memory optimization with DBM before you add Multi\-AZ if your DB instance runs SQL Server 2014, 2016, or 2017 Enterprise Edition and has in\-memory optimization enabled\.   
If your DB instance is running AGs, it doesn't require this step\.


## Common DBA tasks for SQL Server

- **Note**  
When working with a SQL Server DB instance, you can run scripts to modify a newly created database, but you cannot modify the \[model\] database, the database used as the model for new databases\.

