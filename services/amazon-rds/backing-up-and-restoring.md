---
id: Backing up and restoring
title: Backing up and restoring
created: 1683841041000
updated: 1683841041000
---
# Backing up and restoring

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Working with backups

- **Important**  
An outage occurs if you change the backup retention period from 0 to a nonzero value or from a nonzero value to 0\. This applies to both Single\-AZ and Multi\-AZ DB instances\.
- **Note**  
If you manage your backups in AWS Backup, you can't enable automated backups\. For more information, see [Using AWS Backup to manage automated backups](#AutomatedBackups.AWSBackup)\.
- **Note**  
You can only retain automated backups of DB instances, not Multi\-AZ DB clusters\.
- **Important**  
We highly discourage disabling automated backups because it disables point\-in\-time recovery\. Disabling automatic backups for a DB instance or Multi\-AZ DB cluster deletes all existing automated backups for the database\. If you disable and then re\-enable automated backups, you can restore starting only from the time you re\-enabled automated backups\.
- **Note**  
Backups managed by AWS Backup are considered manual DB snapshots, but don't count toward the DB snapshot quota for RDS\. Backups that were created with AWS Backup have names ending in `awsbackup:backup-job-number`\.

