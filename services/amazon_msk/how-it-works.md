---
id: How it works
title: How it works
created: 1683841041000
updated: 1683841041000
---
# How it works

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-msk-developer-guide.git)
{% endhint %}

## Creating a cluster

- **Important**  
You can't change the VPC for an Amazon MSK cluster after you create the cluster\.
- **Important**  
Specify exactly two subnets if you are using one of the following Regions: South America \(São Paulo\), Canada \(Central\), and US West \(N\. California\)\. For other Regions where Amazon MSK is available, you can specify either two or three subnets\. The subnets that you specify must be in distinct Availability Zones\. When you create a cluster, Amazon MSK distributes the broker nodes evenly across the subnets that you specify\.
- **Note**  
The `create-cluster` command might return an error stating that one or more subnets belong to unsupported Availability Zones\. When this happens, the error indicates which Availability Zones are unsupported\. Create subnets that don't use the unsupported Availability Zones and try the `create-cluster` command again\.


## Deleting a cluster

- **Note**  
If your cluster has an auto\-scaling policy, we recommend that you remove the policy before you delete the cluster\. For more information, see [Automatic scaling](msk-autoexpand.md)\.


## Scaling up broker storage

- **Important**  
When storage is scaled for an MSK cluster, the additional storage is made available right away\. However, the cluster requires a cool\-down period after every storage scaling event\. Amazon MSK uses this cool\-down period to optimize the cluster before it can be scaled again\. This period can range from a minimum of 6 hours to over 24 hours, depending on the cluster's storage size and utilization and on traffic\. This is applicable for both auto scaling events and manual scaling using the [UpdateBrokerStorage](https://docs.aws.amazon.com/msk/1.0/apireference/clusters-clusterarn-nodes-storage.html#UpdateBrokerStorage) operation\. For information about right\-sizing your storage, see [Best practices](bestpractices.md)\.


## Updating the broker type

- **Important**  
You can't update a cluster to a smaller broker type if the number of partitions per broker exceeds the maximum number specified in [ Right\-size your cluster: Number of partitions per broker](bestpractices.md#partitions-per-broker)\.


## Expanding a cluster

- **Important**  
If you want to expand an MSK cluster, make sure to use this Amazon MSK operation \. Don't try to add brokers to a cluster without using this operation\.


## Updating security

- **Note**  
The AWS CLI and API operations for updating the security settings of a cluster are idempotent\. This means that if you invoke the security update operation and specify an authentication or encryption setting that is the same setting that the cluster currently has, that setting won't change\.

