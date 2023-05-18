---
id: What is Amazon RDS?
title: What is Amazon RDS?
created: 1683841041000
updated: 1683841041000
---
# What is Amazon RDS?

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## DB instance storage

- **Important**  
When you modify an instance’s storage so that it goes from one volume to four volumes, or when you modify an instance using magnetic storage, Amazon RDS does not use the Elastic Volumes feature\. Instead, Amazon RDS provisions new volumes and transparently moves the data from the old volume to the new volumes\. This operation consumes a significant amount of IOPS and throughput of both the old and new volumes\. Depending on the size of the volume and the amount of database workload present during the modification, this operation can consume a high amount of IOPS, significantly increase IO latency, and take several hours to complete, while the RDS instance remains in the `Modifying` state\.
- **Note**  
DB instances that use General Purpose SSD storage can experience much longer latency after read replica creation, Multi\-AZ conversion, and DB snapshot restoration than instances that use Provisioned IOPS storage\. If you need a DB instance with minimum latency after these operations, we recommend using [Provisioned IOPS SSD storage](#USER_PIOPS)\.
- **Note**  
General Purpose SSD gp3 storage is supported on Single\-AZ and Multi\-AZ DB instances, but isn't supported on Multi\-AZ DB clusters\. For more information, see [Configuring and managing a Multi\-AZ deployment](Concepts.MultiAZ.md) and [Multi\-AZ DB cluster deployments](multi-az-db-clusters-concepts.md)\.
- **Note**  
For SQL Server, the maximum 64,000 IOPS is guaranteed only on [Nitro\-based instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html#ec2-nitro-instances) that are on the m5\*, m6i, r5\*, r6i, and z1d instance types\. Other instance types guarantee performance up to 32,000 IOPS\.  
For Oracle, you can provision the maximum 256,000 IOPS only on the r5b instance type\.
- **Important**  
Depending on the instance class you're using, you might see lower IOPS performance than the maximum that you can provision with RDS\. For specific information on IOPS performance for DB instance classes, see [Amazon EBS–optimized instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-optimized.html) in the *Amazon EC2 User Guide*\. We recommend that you determine the maximum IOPS for the instance class before setting a Provisioned IOPS value for your DB instance\.


## Regions, Availability Zones, and Local Zones

- **Note**  
For information about finding the Availability Zones for an AWS Region, see [Describe your Availability Zones](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html#availability-zones-describe) in the Amazon EC2 documentation\.
- **Note**  
Random selection of Availability Zones by RDS doesn't guarantee an even distribution of DB instances among Availability Zones within a single account or DB subnet group\. You can request a specific AZ when you create or modify a Single\-AZ instance, and you can use more\-specific DB subnet groups for Multi\-AZ instances\. For more information, see [Creating an Amazon RDS DB instance](USER_CreateDBInstance.md) and [Modifying an Amazon RDS DB instance](Overview.DBInstance.Modifying.md)\.
- **Note**  
A Local Zone can't be included in a Multi\-AZ deployment\.
- **Important**  
Currently, the only AWS Local Zone where Amazon RDS is available is Los Angeles in the US West \(Oregon\) Region\.

