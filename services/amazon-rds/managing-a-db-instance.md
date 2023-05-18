---
id: Managing a DB instance
title: Managing a DB instance
created: 1683841041000
updated: 1683841041000
---
# Managing a DB instance

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Stopping a DB instance

- **Note**  
In some cases, a large amount of time is required to stop a DB instance\. If you want to stop your DB instance and restart it immediately, you can reboot the DB instance\. For information about rebooting a DB instance, see [Rebooting a DB instance](USER_RebootInstance.md)\.
- **Note**  
For a Multi\-AZ deployment, a large amount of time might be required to stop a DB instance\. If you have at least one backup after a previous failover, then you can speed up the stop DB instance operation\. To do so, perform a reboot with failover operation before stopping the DB instance\.
- **Important**  
You can stop a DB instance for up to seven days\. If you don't manually start your DB instance after seven days, your DB instance is automatically started\. This way, it doesn't fall behind any required maintenance updates\.
- **Note**  
You should always connect to a DB instance using the DNS endpoint, not the IP address\.


## Connecting an EC2 instance

- **Note**  
You can only set up a connection between an EC2 instance and an RDS database automatically by using the AWS Management Console\. You can't set up a connection automatically with the AWS CLI or RDS API\.


## Modifying a DB instance

- **Important**  
Some modifications result in downtime because Amazon RDS must reboot your DB instance for the change to take effect\. Review the impact to your database and applications before modifying your DB instance settings\.
- **Important**  
If any of the pending modifications require the DB instance to be temporarily unavailable \(*downtime*\), choosing the apply immediately option can cause unexpected downtime\.  
When you choose to apply a change immediately, any pending modifications are also applied immediately, instead of during the next maintenance window\.   
If you don't want a pending change to be applied in the next maintenance window, you can modify the DB instance to revert the change\. You can do this by using the AWS CLI and specifying the `--apply-immediately` option\.


## Maintaining a DB instance

- **Note**  
To defer a maintenance action, specify `undo-opt-in` for `--opt-in-type`\. You can't specify `undo-opt-in` for `--opt-in-type` if the maintenance action has already started\.  
To cancel a maintenance action, run the [modify\-db\-instance](https://docs.aws.amazon.com/cli/latest/reference/rds/modify-db-instance.html) AWS CLI command and specify `--no-auto-minor-version-upgrade`\.
- **Note**  
Staying current on all optional and mandatory updates might be required to meet various compliance obligations\. We recommend that you apply all updates made available by RDS routinely during your maintenance windows\.
- **Note**  
The dates in the table apply to customers who didn't experience mandatory operating system updates in 2022\. To confirm whether the mandatory operating system updates in 2023 impact you, check the **Pending maintenance** section in the console for operating system updates\. For more information, see the Console section under [Working with operating system updates](#OS_Updates)\.


## Upgrading the engine version

- **Important**  
You can't modify a DB instance when it is being upgraded\. During an upgrade, the DB instance status is `upgrading`\.
- **Note**  
Database engine upgrades require downtime\. You can minimize the downtime required for DB instance upgrade by using a blue/green deployment\. For more information, see [Using Amazon RDS Blue/Green Deployments for database updates](blue-green-deployments.md)\.
- **Important**  
If you plan to migrate an RDS for PostgreSQL DB instance to an Aurora PostgreSQL DB cluster soon, we strongly recommend that you turn off auto minor version upgrades for the DB instance early during planning\. Migration to Aurora PostgreSQL might be delayed if the RDS for PostgreSQL version isn't yet supported by Aurora PostgreSQL\. For information about Aurora PostgreSQL versions, see [ Engine versions for Amazon Aurora PostgreSQL](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/AuroraPostgreSQL.Updates.20180305.html)\.


## Renaming a DB instance

- **Note**  
A DB instance is an isolated database environment running in the cloud\. A DB instance can host multiple databases, or a single Oracle database with multiple schemas\. For information about changing a database name, see the documentation for your DB engine\.
- **Important**  
The DB instance is rebooted when it is renamed\.


## Rebooting a DB instance

- **Note**  
If a DB instance isn't using the latest changes to its associated DB parameter group, the AWS Management Console shows the DB parameter group with a status of **pending\-reboot**\. The **pending\-reboot** parameter groups status doesn't result in an automatic reboot during the next maintenance window\. To apply the latest parameter changes to that DB instance, manually reboot the DB instance\. For more information about parameter groups, see [Working with parameter groups](USER_WorkingWithParamGroups.md)\.
- **Note**  
When you force a failover from one Availability Zone to another when you reboot, the Availability Zone change might not be reflected in the AWS Management Console, and in calls to the AWS CLI and RDS API, for several minutes\.


## Working with DB instance read replicas

- **Note**  
The information following applies to creating Amazon RDS read replicas either in the same AWS Region as the source DB instance, or in a separate AWS Region\. The information following doesn't apply to setting up replication with an instance that is running on an Amazon EC2 instance or that is on\-premises\.
- **Note**  
The Oracle DB engine supports replica databases in mounted mode\. A mounted replica doesn't accept user connections and so can't serve a read\-only workload\. The primary use for mounted replicas is cross\-Region disaster recovery\. For more information, see [Working with read replicas for Amazon RDS for Oracle](oracle-read-replicas.md)\.
- **Note**  
When you increase the allocated storage of a read replica, it must be by at least 10 percent\. If you try to increase the value by less than 10 percent, you get an error\.
- **Note**  
The I/O suspension typically lasts about one minute\. You can avoid the I/O suspension if the source DB instance is a Multi\-AZ deployment, because in that case the snapshot is taken from the secondary DB instance\.
- **Note**  
Within an AWS Region, we strongly recommend that you create all read replicas in the same virtual private cloud \(VPC\) based on Amazon VPC as the source DB instance\. If you create a read replica in a different VPC from the source DB instance, classless inter\-domain routing \(CIDR\) ranges can overlap between the replica and the RDS system\. CIDR overlap makes the replica unstable, which can negatively impact applications connecting to it\. If you receive an error when creating the read replica, choose a different destination DB subnet group\. For more information, see [Working with a DB instance in a VPC](USER_VPC.WorkingWithRDSInstanceinaVPC.md)\.  
You can't create a read replica in a different AWS account from the source DB instance\.
- **Note**  
Previous versions of MariaDB and MySQL used `SHOW SLAVE STATUS` instead of `SHOW REPLICA STATUS`\. If you are using a MariaDB version before 10\.5 or a MySQL version before 8\.0\.23, then use `SHOW SLAVE STATUS`\.
- **Note**  
New databases aren't included in the lag calculation until they are accessible on the read replica\.
- **Note**  
To create an encrypted read replica in a different AWS Region from the source DB instance, the source DB instance must be encrypted\.


## Tagging RDS resources

- **Note**  
Currently, you can't tag RDS Proxies and RDS Proxy endpoints by using the AWS Management Console\.
- **Note**  
You can add a tag to a snapshot, however, your bill will not reflect this grouping\.
- **Note**  
In some cases, you might include a value for the `--tag-key` parameter of the [create\-db\-snapshot](https://docs.aws.amazon.com/cli/latest/reference/rds/create-db-snapshot.html) AWS CLI command\. Or you might supply at least one tag to the [CreateDBSnapshot](https://docs.aws.amazon.com/AmazonRDS/latest/APIReference/API_CreateDBSnapshot.html) API operation\. In these cases, RDS doesn't copy tags from the source DB instance to the new DB snapshot\. This functionality applies even if the source DB instance has the `--copy-tags-to-snapshot` \(`CopyTagsToSnapshot`\) option turned on\.   
If you take this approach, you can create a copy of a DB instance from a DB snapshot\. This approach avoids adding tags that don't apply to the new DB instance\. You create your DB snapshot using the AWS CLI `create-db-snapshot` command \(or the `CreateDBSnapshot` RDS API operation\)\. After you create your DB snapshot, you can add tags as described later in this topic\.
- **Tip**  
You can use assigning tags and finding DB instances with those tags to reduce costs in other ways\. For example, take this scenario with DB instances used for development and testing\. In this case, you might designate some DB instances to be deleted at the end of each day\. Or you might designate them to have their DB instances changed to small DB instance classes during times of expected low usage\.


## Working with storage

- **Note**  
Scaling storage for Amazon RDS for Microsoft SQL Server DB instances is supported only for General Purpose SSD or Provisioned IOPS SSD storage types\.
- **Note**  
Storage optimization can take several hours\. You can't make further storage modifications for either six \(6\) hours or until storage optimization has completed on the instance, whichever is longer\.
- **Note**  
You can't reduce the amount of storage for a DB instance after storage has been allocated\. When you increase the allocated storage, it must be by at least 10 percent\. If you try to increase the value by less than 10 percent, you get an error\.
- **Note**  
We recommend that you carefully choose the maximum storage threshold based on usage patterns and customer needs\. If there are any aberrations in the usage patterns, the maximum storage threshold can prevent scaling storage to an unexpectedly high value when autoscaling predicts a very high threshold\. After a DB instance has been autoscaled, its allocated storage can't be reduced\.
- **Note**  
When you clone an Amazon RDS DB instance that has storage autoscaling enabled, that setting isn't automatically inherited by the cloned instance\. The new DB instance has the same amount of allocated storage as the original instance\. You can turn storage autoscaling on again for the new instance if the cloned instance continues to increase its storage requirements\.
- **Note**  
Storage optimization can take several hours\. You can't make further storage modifications for either six \(6\) hours or until storage optimization has completed on the instance, whichever is longer\.
- **Note**  
You can't make further storage modifications until six \(6\) hours after storage optimization has completed on the instance\.


## Deleting a DB instance

- **Note**  
You can't delete a DB instance when deletion protection is turned on\. For more information, see [Prerequisites for deleting a DB instance](#USER_DeleteInstance.DeletionProtection)\.

