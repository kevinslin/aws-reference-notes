---
id: Managing an Aurora DB cluster
title: Managing an Aurora DB cluster
created: 1683841041000
updated: 1683841041000
---
# Managing an Aurora DB cluster

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Stopping and starting a cluster

- **Important**  
You can stop a DB cluster for up to seven days\. If you don't manually start your DB cluster after seven days, your DB cluster is automatically started so that it doesn't fall behind any required maintenance updates\.


## Connecting an EC2 instance

- **Note**  
You can only set up a connection between an EC2 instance and an Aurora DB cluster automatically by using the AWS Management Console\. You can't set up a connection automatically with the AWS CLI or RDS API\.


## Modifying an Aurora DB cluster

- **Note**  
Most modifications can be applied immediately or during the next scheduled maintenance window\. Some modifications, such as turning on deletion protection and changing the master password, are applied immediately—regardless of when you choose to apply them\.  
If you're using SSL endpoints and change the DB cluster identifier, stop and restart the DB cluster to update the SSL endpoints\. For more information, see [Stopping and starting an Amazon Aurora DB cluster](aurora-cluster-stop-start.md)\.
- **Note**  
Some settings only apply to DB instances\. To change those settings, follow the instructions in [Modifying a DB instance in a DB cluster](#Aurora.Modifying.Instance)\.
- **Note**  
Some settings only apply to DB instances\. To change those settings, follow the instructions in [Modifying a DB instance in a DB cluster](#Aurora.Modifying.Instance)\.
- **Important**  
If any of the deferred modifications require downtime, choosing **Apply immediately** can cause unexpected downtime for the DB instance\. There is no downtime for the other DB instances in the DB cluster\.   
 Modifications that you defer aren't listed in the output of the `describe-pending-maintenance-actions` CLI command\. Maintenance actions only include system upgrades that you schedule for the next maintenance window\.
- **Note**  
Some settings apply to the entire DB cluster\. To change those settings, follow the instructions in [Modifying the DB cluster by using the console, CLI, and API](#Aurora.Modifying.Cluster)\.
- **Note**  
Some settings apply to the entire DB cluster\. To change those settings, follow the instructions in [Modifying the DB cluster by using the console, CLI, and API](#Aurora.Modifying.Cluster)\.
- **Note**  
Additional settings are available if you are modifying an Aurora Serverless v1 or Aurora Serverless v2 DB cluster\. For information about these settings, see [Modifying an Aurora Serverless v1 DB cluster](aurora-serverless.modifying.md) and [Managing Aurora Serverless v2](aurora-serverless-v2-administration.md)\.  
Some settings aren't available for Aurora Serverless v1 and Aurora Serverless v2 because of their limitations\. For more information, see [Limitations of Aurora Serverless v1](aurora-serverless.md#aurora-serverless.limitations) and [Requirements for Aurora Serverless v2](aurora-serverless-v2.requirements.md)\.
- **Note**  
You can't use the AWS Management Console to modify these settings for Aurora DB clusters\.
- **Note**  
You can't use the AWS Management Console to modify these settings for Aurora DB instances\.


## Adding Aurora Replicas

- **Note**  
Amazon Aurora also supports replication with an external database, such as an RDS DB instance\. The RDS DB instance must be in the same AWS Region as Amazon Aurora\. For more information, see [Replication with Amazon Aurora](Aurora.Replication.md)\.


## Managing performance and scaling

- **Note**  
For Aurora MySQL, the `innodb_file_per_table` parameter affects how table storage is organized\. When tables are part of the system tablespace, dropping the table doesn't reduce the size of the system tablespace\. Thus, make sure to set `innodb_file_per_table` to 1 for Aurora MySQL DB clusters to take full advantage of dynamic resizing\.  
For Aurora MySQL version 2\.10 and higher, the InnoDB temporary tablespace is dropped and re\-created on restart\. This releases the space occupied by the temporary tablespace to the system, and then the cluster volume resizes\. To take full advantage of the dynamic resizing feature, we recommend that you upgrade your DB cluster to Aurora MySQL version 2\.10 or higher\.  
The dynamic resizing feature reclaims space from dropped tablespaces over time, not immediately, when tables in those tablespaces are dropped\. Space in the system tablespace isn't reclaimed because the system tablespace is never removed\. Unreclaimed free space in a tablespace is reused when an operation needs space in that tablespace\.
- **Tip**  
If your applications frequently open and close connections, or keep a large number of long\-lived connections open, we recommend that you use Amazon RDS Proxy\. RDS Proxy is a fully managed, highly available database proxy that uses connection pooling to share database connections securely and efficiently\. To learn more about RDS Proxy, see [Using Amazon RDS Proxy for Aurora](rds-proxy.md)\.


## Cloning a volume for an Aurora DB cluster

- **Note**  
 The [restore\-db\-cluster\-to\-point\-in\-time](https://docs.aws.amazon.com/cli/latest/reference/rds/restore-db-cluster-to-point-in-time.html) AWS CLI command only restores the DB cluster, not the DB instances for that DB cluster\. You must invoke the [create\-db\-instance](https://docs.aws.amazon.com/cli/latest/reference/rds/create-db-instance.html) command to create DB instances for the restored DB cluster, specifying the identifier of the restored DB cluster in `--db-cluster-identifier`\. You can create DB instances only after the `restore-db-cluster-to-point-in-time` command has completed and the DB cluster is available\.
- **Note**  
The [restore\-db\-cluster\-to\-point\-in\-time](https://docs.aws.amazon.com/cli/latest/reference/rds/restore-db-cluster-to-point-in-time.html) AWS CLI command restores only the DB cluster, not the DB instances for that DB cluster\. To create DB instances for the restored DB cluster, invoke the [create\-db\-instance](https://docs.aws.amazon.com/cli/latest/reference/rds/create-db-instance.html) command\. Specify the identifier of the restored DB cluster in `--db-cluster-identifier`\.   
You can create DB instances only after the `restore-db-cluster-to-point-in-time` command has completed and the DB cluster is available\.
- **Note**  
The [RestoreDBClusterToPointInTime](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_RestoreDBClusterToPointInTime.html) RDS API operation restores only the DB cluster, not the DB instances for that DB cluster\. To create DB instances for the restored DB cluster, invoke the [CreateDBInstance](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBInstance.html) RDS API operation\. Specify the identifier of the restored DB cluster in `DBClusterIdentifier`\. You can create DB instances only after the `RestoreDBClusterToPointInTime` operation has completed and the DB cluster is available\.


## Maintaining an Aurora DB cluster

- **Note**  
To defer a maintenance action, specify `undo-opt-in` for `--opt-in-type`\. You can't specify `undo-opt-in` for `--opt-in-type` if the maintenance action has already started\.  
To cancel a maintenance action, run the [modify\-db\-instance](https://docs.aws.amazon.com/cli/latest/reference/rds/modify-db-instance.html) AWS CLI command and specify `--no-auto-minor-version-upgrade`\.
- **Note**  
This setting is enabled by default\. For each new cluster, choose the appropriate value for this setting\. This value is based on its importance, expected lifetime, and the amount of verification testing that you do after each upgrade\.
- **Note**  
Staying current on all optional and mandatory updates might be required to meet various compliance obligations\. We recommend that you apply all updates made available by RDS routinely during your maintenance windows\.


## Rebooting an Aurora DB cluster or instance

- **Note**  
 If a DB instance isn't using the latest changes to its associated DB parameter group, the AWS Management Console shows the DB parameter group with a status of **pending\-reboot**\. The **pending\-reboot** parameter groups status doesn't result in an automatic reboot during the next maintenance window\. To apply the latest parameter changes to that DB instance, manually reboot the DB instance\. For more information about parameter groups, see [Working with parameter groups](USER_WorkingWithParamGroups.md)\.
- **Important**  
 In Aurora MySQL 2\.10 and higher, the reboot behavior is different: the reader DB instances typically remain available while you reboot the writer instance\. Then you can reboot the reader instances at a convenient time\. You can reboot the reader instances on a staggered schedule if you want some reader instances to always be available\. For more information, see [Rebooting an Aurora MySQL cluster \(version 2\.10 and higher\)](#aurora-mysql-survivable-replicas)\.
- **Important**  
 The change to reboot behavior in Aurora MySQL 2\.10 and higher is different for Aurora global databases\. If you reboot the writer instance for the primary cluster in an Aurora global database, the reader instances in the primary cluster remain available\. However, the DB instances in any secondary clusters reboot at the same time\.
- **Tip**  
 Aurora MySQL might still reboot some of the reader instances along with the writer instance if your cluster is processing a workload with high throughput\.   
 The reduction in the number of reboots applies during failover operations also\. Aurora MySQL only restarts the writer DB instance and the failover target during a failover\. Other reader DB instances in the cluster remain available to continue processing queries through connections to the reader endpoint\. Thus, you can improve availability during a failover by having more than one reader DB instance in a cluster\.
- **Tip**  
 For long\-term monitoring, we recommend monitoring the `EngineUptime` metric for individual instances instead of at the cluster level\. The cluster\-level `EngineUptime` metric is set to zero when a new DB instance is added to the cluster\. Such cluster changes can happen as part of maintenance and scaling operations such as those performed by Auto Scaling\.


## Deleting Aurora clusters and instances

- **Tip**  
 You can keep a cluster with no DB instances to preserve your data without incurring CPU charges for the cluster\. You can quickly start using the cluster again by creating one or more new DB instances for the cluster\. You can perform Aurora\-specific administrative operations on the cluster while it doesn't have any associated DB instances\. You just can't access the data or perform any operations that require connecting to a DB instance\.
- **Tip**  
 Even if all the DB instances are deleted, you can access the data by creating a new DB instance in the cluster\.
- **Note**  
When an Aurora Replica is deleted, its instance endpoint is removed immediately, and the Aurora Replica is removed from the reader endpoint\. If there are statements running on the Aurora Replica that is being deleted, there is a three\-minute grace period\. Existing statements can finish during the grace period\. When the grace period ends, the Aurora Replica is shut down and deleted\.
- **Note**  
You can't delete a DB cluster when deletion protection is enabled for it\. For more information, see [Deletion protection for Aurora clusters](#USER_DeletionProtection)\.   
You can disable deletion protection by modifying the DB cluster\. For more information, see [Modifying an Amazon Aurora DB cluster](Aurora.Modifying.md)\.
- **Note**  
 When the status for a DB instance is `deleting`, its CA certificate value doesn't appear in the RDS console or in output for AWS CLI commands or RDS API operations\. For more information about CA certificates, see [Using SSL/TLS to encrypt a connection to a DB cluster](UsingWithRDS.SSL.md)\.


## Tagging RDS resources

- **Note**  
Currently, you can't tag RDS Proxies and RDS Proxy endpoints by using the AWS Management Console\.
- **Note**  
You can add a tag to a snapshot, however, your bill will not reflect this grouping\.
- **Note**  
In some cases, you might include a value for the `--tag-key` parameter of the [create\-db\-snapshot](https://docs.aws.amazon.com/cli/latest/reference/rds/create-db-snapshot.html) AWS CLI command\. Or you might supply at least one tag to the [CreateDBSnapshot](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBSnapshot.html) API operation\. In these cases, RDS doesn't copy tags from the source DB instance to the new DB snapshot\. This functionality applies even if the source DB instance has the `--copy-tags-to-snapshot` \(`CopyTagsToSnapshot`\) option turned on\.   
If you take this approach, you can create a copy of a DB instance from a DB snapshot\. This approach avoids adding tags that don't apply to the new DB instance\. You create your DB snapshot using the AWS CLI `create-db-snapshot` command \(or the `CreateDBSnapshot` RDS API operation\)\. After you create your DB snapshot, you can add tags as described later in this topic\.
- **Tip**  
You can use assigning tags and finding clusters that have those tags to reduce costs in other ways\. For example, take the scenario with Aurora DB clusters used for development and testing\. Here, you might designate some clusters to be deleted at the end of each day, or to have only their reader DB instances deleted\. Or you might designate some to have their DB instances changed to small DB instance classes during times of expected low usage\.


## Aurora updates

- **Note**  
The time required to reboot your DB instance depends on the crash recovery process, database activity at the time of reboot, and the behavior of your specific DB engine\. To improve the reboot time, we recommend that you reduce database activity as much as possible during the reboot process\. Reducing database activity reduces rollback activity for in\-transit transactions\.

