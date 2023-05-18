---
id: Backing up and restoring an Aurora DB cluster
title: Backing up and restoring an Aurora DB cluster
created: 1683841041000
updated: 1683841041000
---
# Backing up and restoring an Aurora DB cluster

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Overview of backing up and restoring

- **Note**  
For Amazon Aurora DB clusters, the default backup retention period is one day regardless of how the DB cluster is created\.
You can't disable automated backups on Aurora\. The backup retention period for Aurora is managed by the DB cluster\.
- **Note**  
You can also use AWS Backup to manage backups of Amazon Aurora DB clusters\. Backups managed by AWS Backup are considered manual DB cluster snapshots, but don't count toward the DB cluster snapshot quota for Aurora\. Backups that were created with AWS Backup have names ending in `awsbackup:AWS-Backup-job-number`\. For information about AWS Backup, see the [https://docs.aws.amazon.com/aws-backup/latest/devguide](https://docs.aws.amazon.com/aws-backup/latest/devguide)\.
- **Note**  
When you create a DB cluster using the AWS Management Console, you can't specify a backup window\. However, you can specify a backup window when you create a DB cluster using the AWS CLI or RDS API\.


## Creating a DB cluster snapshot

- **Note**  
Your DB cluster must be in the `available` state to take a DB cluster snapshot\.


## Restoring from a DB cluster snapshot

- **Note**  
Sharing a manual DB cluster snapshot, whether encrypted or unencrypted, enables authorized AWS accounts to directly restore a DB cluster from the snapshot instead of taking a copy of it and restoring from that\. For more information, see [Sharing a DB cluster snapshot](aurora-share-snapshot.md)\.
- **Important**  
If you use the console to restore a DB cluster, then Amazon RDS automatically creates the primary instance \(writer\) for your DB cluster\. If you use the AWS CLI to restore a DB cluster, you must explicitly create the primary instance for your DB cluster\. The primary instance is the first instance that is created in a DB cluster\. Call the [create\-db\-instance](https://docs.aws.amazon.com/cli/latest/reference/rds/create-db-instance.html) AWS CLI command to create the primary instance for your DB cluster\. Include the name of the DB cluster as the `--db-cluster-identifier` option value\.
- **Important**  
If you use the console to restore a DB cluster, then Amazon RDS automatically creates the primary instance \(writer\) for your DB cluster\. If you use the RDS API to restore a DB cluster, you must explicitly create the primary instance for your DB cluster\. The primary instance is the first instance that is created in a DB cluster\. Call the RDS API operation [ CreateDBInstance](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBInstance.html) to create the primary instance for your DB cluster\. Include the name of the DB cluster as the `DBClusterIdentifier` parameter value\.


## Copying a DB cluster snapshot

- **Note**  
Amazon bills you based upon the amount of Amazon Aurora backup and snapshot data you keep and the period of time that you keep it\. For information about the storage associated with Aurora backups and snapshots, see [Understanding Amazon Aurora backup storage usage](aurora-storage-backup.md)\. For pricing information about Aurora storage, see [Amazon RDS for Aurora pricing](https://aws.amazon.com/rds/aurora/pricing)\.
- **Note**  
For Amazon Aurora DB cluster snapshots, you can't encrypt an unencrypted DB cluster snapshot when you copy the snapshot\.


## Sharing a DB cluster snapshot

- **Note**  
To share an automated DB cluster snapshot, create a manual DB cluster snapshot by copying the automated snapshot, and then share that copy\. This process also applies to AWS Backup–generated resources\.


## Exporting DB cluster data to Amazon S3

- **Note**  
The S3 bucket must be in the same AWS Region as the DB cluster\.
- **Important**  
If you plan to use the AWS Management Console to export your DB cluster, you can choose to create the IAM policy and the role automatically when you export the DB cluster\. For instructions, see [Exporting DB cluster data to an Amazon S3 bucket](#export-cluster-data.Exporting)\.
- **Note**  
Exporting DB cluster data can take a while depending on your database type and size\. The export task first clones and scales the entire database before extracting the data to Amazon S3\. The task's progress during this phase displays as **Starting**\. When the task switches to exporting data to S3, progress displays as **In progress**\.  
The time it takes for the export to complete depends on the data stored in the database\. For example, tables with well\-distributed numeric primary key or index columns export the fastest\. Tables that don't contain a column suitable for partitioning and tables with only one index on a string\-based column take longer because the export uses a slower single\-threaded process\.
- **Note**  
Canceling an export task doesn't remove any data that was exported to Amazon S3\. For information about how to delete the data using the console, see [ How do I delete objects from an S3 bucket?](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/delete-objects.html) To delete the data using the CLI, use the [delete\-object](https://docs.aws.amazon.com/cli/latest/reference/s3api/delete-object.html) command\.


## Exporting DB cluster snapshot data to Amazon S3

- **Note**  
The S3 bucket to export to must be in the same AWS Region as the snapshot\.
- **Important**  
If you plan to use the AWS Management Console to export your snapshot, you can choose to create the IAM policy and the role automatically when you export the snapshot\. For instructions, see [Exporting a snapshot to an Amazon S3 bucket](#aurora-export-snapshot.Exporting)\.
- **Note**  
Exporting RDS snapshots can take a while depending on your database type and size\. The export task first restores and scales the entire database before extracting the data to Amazon S3\. The task's progress during this phase displays as **Starting**\. When the task switches to exporting data to S3, progress displays as **In progress**\.  
The time it takes for the export to complete depends on the data stored in the database\. For example, tables with well\-distributed numeric primary key or index columns export the fastest\. Tables that don't contain a column suitable for partitioning and tables with only one index on a string\-based column take longer\. This longer export time occurs because the export uses a slower single\-threaded process\.
- **Note**  
Canceling a snapshot export task doesn't remove any data that was exported to Amazon S3\. For information about how to delete the data using the console, see [ How do I delete objects from an S3 bucket?](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/delete-objects.html) To delete the data using the CLI, use the [delete\-object](https://docs.aws.amazon.com/cli/latest/reference/s3api/delete-object.html) command\.


## Point-in-time recovery

- **Note**  
Information in this topic applies to Amazon Aurora\. For information on restoring an Amazon RDS DB instance, see [Restoring a DB instance to a specified time](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_PIT.html)\.  
For more information about backing up and restoring an Aurora DB cluster, see [Overview of backing up and restoring an Aurora DB cluster](Aurora.Managing.Backups.md)\.  
For Aurora MySQL, you can restore a provisioned DB cluster to an Aurora Serverless DB cluster\. For more information, see [Restoring an Aurora Serverless v1 DB cluster](aurora-serverless.restorefromsnapshot.md)\.
- **Important**  
If you use the console to restore a DB cluster to a specified time, then Amazon RDS automatically creates the primary instance \(writer\) for your DB cluster\. If you use the AWS CLI to restore a DB cluster to a specified time, you must explicitly create the primary instance for your DB cluster\. The primary instance is the first instance that is created in a DB cluster\.   
To create the primary instance for your DB cluster, call the [create\-db\-instance](https://docs.aws.amazon.com/cli/latest/reference/rds/create-db-instance.html) AWS CLI command\. Include the name of the DB cluster as the `--db-cluster-identifier` option value\.
- **Important**  
If you use the console to restore a DB cluster to a specified time, then Amazon RDS automatically creates the primary instance \(writer\) for your DB cluster\. If you use the RDS API to restore a DB cluster to a specified time, make sure to explicitly create the primary instance for your DB cluster\. The primary instance is the first instance that is created in a DB cluster\.   
To create the primary instance for your DB cluster, call the RDS API operation [ CreateDBInstance](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBInstance.html)\. Include the name of the DB cluster as the `DBClusterIdentifier` parameter value\.


## Deleting a DB cluster snapshot

- **Note**  
To delete backups managed by AWS Backup, use the AWS Backup console\. For information about AWS Backup, see the [https://docs.aws.amazon.com/aws-backup/latest/devguide](https://docs.aws.amazon.com/aws-backup/latest/devguide)\.


## Tutorial: Restore a DB cluster from a snapshot

- **Note**  
While the primary DB instance is being created, it appears as a reader instance, but after creation it's a writer instance\.

