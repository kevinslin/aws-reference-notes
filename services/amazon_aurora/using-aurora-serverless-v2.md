---
id: Using Aurora Serverless v2
title: Using Aurora Serverless v2
created: 1683841041000
updated: 1683841041000
---
# Using Aurora Serverless v2

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## How Aurora Serverless v2 works

- **Important**  
 With Aurora Serverless v1, your cluster has a single measure of compute capacity that can scale between the minimum and maximum capacity values\. With Aurora Serverless v2, your cluster can contain readers in addition to the writer\. Each Aurora Serverless v2 writer and reader can scale between the minimum and maximum capacity values\. Thus, the total capacity of your Aurora Serverless v2 cluster depends on both the capacity range that you define for your DB cluster and the number of writers and readers in the cluster\. At any specific time, you are only charged for the Aurora Serverless v2 capacity that is being actively used in your Aurora DB cluster\.
- **Note**  
 Currently, Aurora Serverless v2 writers and readers don't scale all the way down to zero ACUs\. Idle Aurora Serverless v2 writers and readers can scale down to the minimum ACU value that you specified for the cluster\.   
 That behavior is different than Aurora Serverless v1, which can pause after a period of idleness, but then takes some time to resume when you open a new connection\. When your DB cluster with Aurora Serverless v2 capacity isn't needed for some time, you can stop and start clusters as with provisioned DB clusters\. For details about stopping and starting clusters, see [Stopping and starting an Amazon Aurora DB cluster](aurora-cluster-stop-start.md)\.


## Getting started with Aurora Serverless v2

- **Important**  
 When you perform a major version upgrade to an Aurora Serverless v2\-compatible version by using snapshot restore or cloning, the first DB instance that you add to the new cluster must be a provisioned DB instance\. This addition starts the final stage of the upgrade process\.   
 Until that final stage happens, the cluster doesn't have the infrastructure that's required for Aurora Serverless v2 support\. Thus, these upgraded clusters always start with a provisioned writer DB instance\. Then you can convert or fail over the provisioned DB instance to an Aurora Serverless v2 one\.


## Creating a cluster for Aurora Serverless v2

- **Tip**  
 A simple way to set up a new cluster where you can use Aurora Serverless v2 is to choose the **Easy create** setting on the console **Create database** page\. With that setting, you only make a single other choice: whether the cluster is intended for development and test use or for production\. Both of those options set up a cluster with an Aurora Serverless v2 writer DB instance\.
- **Note**  
When you create an Aurora Serverless v2 DB cluster using the AWS CLI, the engine mode appears in the output as `provisioned` rather than `serverless`\. The `serverless` engine mode refers to Aurora Serverless v1\.
- **Tip**  
 If you don't specify the minimum and maximum ACUs when you create the cluster, you can use the `modify-db-cluster` command afterward to add that setting\. Until you do, you can't add any Aurora Serverless v2 DB instances to the cluster\. If you try to add a `db.serverless` DB instance, you get an error\.
- **Tip**  
 If you don't specify the minimum and maximum ACUs when you create the cluster, you can use the `ModifyDBCluster` operation afterward to add that setting\. Until you do, you can't add any Aurora Serverless v2 DB instances to the cluster\. If you try to add a `db.serverless` DB instance, you get an error\.


## Managing Aurora Serverless v2

- **Note**  
When you modify the capacity range for an Aurora Serverless v2 DB cluster, the change takes place immediately, regardless of whether you choose to apply it immediately or during the next scheduled maintenance window\.
- **Tip**  
 Some of the older DB instance classes such as db\.r3 and db\.t2 aren't available for the Aurora versions that you use with Aurora Serverless v2\. To see which DB instance classes you can use when converting an Aurora Serverless v2 DB instance to a provisioned one, see [Supported DB engines for DB instance classes](Concepts.DBInstanceClass.md#Concepts.DBInstanceClass.SupportAurora)\.
- **Note**  
For Aurora Serverless v2, you can create both DB cluster and DB parameter groups\. This contrasts with Aurora Serverless v1, where you can only create DB cluster parameter groups\.
- **Note**  
For Aurora MySQL–compatible Aurora Serverless v2 DB clusters, the error log includes buffer pool scaling events even when there are no errors\.


## Performance and scaling for Aurora Serverless v2

- **Tip**  
You can reboot the DB instances yourself to apply these parameter changes\. Or you can wait for Aurora to do the reboot and apply the parameter changes during your next scheduled maintenance window\.
- **Note**  
The `max_connections` value for Aurora Serverless v2DB instances is based on the memory size derived from the maximum ACUs\. However, when you specify a minimum capacity of 0\.5 ACUs on PostgreSQL\-compatible DB instances, the maximum value of `max_connections` is capped at 2,000\.

