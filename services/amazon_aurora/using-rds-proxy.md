---
id: Using RDS Proxy
title: Using RDS Proxy
created: 1683841041000
updated: 1683841041000
---
# Using RDS Proxy

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## RDS Proxy concepts and terminology

- **Note**  
 RDS Proxy uses certificates from the AWS Certificate Manager \(ACM\)\. If you are using RDS Proxy, you don't need to download Amazon RDS certificates or update applications that use RDS Proxy connections\.


## Getting started with RDS Proxy

- **Note**  
RDS Proxy never uses more than 215 IP addresses in a VPC\.
- **Tip**  
 The following procedure applies if you use the IAM console\. If you use the AWS Management Console for RDS, RDS can create the IAM policy for you automatically\. In that case, you can skip the following procedure\.
- **Tip**  
 If you don't already know the subnet IDs to use for the `--vpc-subnet-ids` parameter, see [Setting up network prerequisites](#rds-proxy-network-prereqs) for examples of how to find them\.
- **Note**  
The security group must allow access to the database the proxy connects to\. The same security group is used for ingress from your applications to the proxy, and for egress from the proxy to the database\. For example, suppose that you use the same security group for your database and your proxy\. In this case, make sure that you specify that resources in that security group can communicate with other resources in the same security group\.  
When using a shared VPC, you can't use the default security group for the VPC, or one that belongs to another account\. Choose a security group that belongs to your account\. If one doesn't exist, create one\. For more information about this limitation, see [Work with shared VPCs](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-sharing.html#vpc-share-limitations)\.


## Managing an RDS Proxy

- **Important**  
The values in the **Client authentication type** and **IAM authentication** fields apply to all Secrets Manager secrets that are associated with this proxy\. To specify different values for each secret, modify your proxy by using the AWS CLI or the API instead\.
- **Important**  
If the DB cluster is part of a global database with write forwarding turned on, reduce your proxy's `MaxConnectionsPercent` value by the quota that's allotted for write forwarding\. The write forwarding quota is set in the DB cluster parameter `aurora_fwd_writer_max_connections_pct`\. For information about write forwarding, see [Using write forwarding in an Amazon Aurora global database](aurora-global-database-write-forwarding.md)\.
- **Note**  
RDS Proxy closes database connections some time after 24 hours when they are no longer in use\. The proxy performs this action regardless of the value of the maximum idle connections setting\.


## Working with RDS Proxy endpoints

- **Tip**  
 When you create a proxy for an Aurora cluster using the AWS Management Console, you can have RDS Proxy automatically create a reader endpoint\. For information about the benefits of a reader endpoint, see [Using reader endpoints with Aurora clusters](#rds-proxy-endpoints-reader)\.
- **Note**  
 When you specify that a new endpoint is read\-only, RDS Proxy requires that the Aurora cluster has one or more reader DB instances\. In some cases, you might change the target of the proxy to an Aurora cluster containing only a single writer or a multi\-writer Aurora cluster\. If you do, any requests to the reader endpoint fail with an error\. Requests also fail if the target of the proxy is an RDS instance instead of an Aurora cluster\.   
 If an Aurora cluster has reader instances but those instances aren't available, RDS Proxy waits to send the request instead of returning an error immediately\. If no reader instance becomes available within the connection borrow timeout period, the request fails with an error\.
- **Tip**  
 Don't rely only on checking the DB instance name to determine whether the connection is read/write or read\-only\. Remember that DB instances in an Aurora cluster can change roles between writer and reader when failovers happen\.
- **Note**  
 You can't delete the default endpoint that RDS Proxy automatically creates for each proxy\.   
 When you delete a proxy, RDS Proxy automatically deletes all the associated endpoints\.


## Monitoring RDS Proxy with CloudWatch

- **Note**  
 RDS publishes these metrics for each underlying Amazon EC2 instance associated with a proxy\. A single proxy might be served by more than one EC2 instance\. Use CloudWatch statistics to aggregate the values for a proxy across all the associated instances\.   
 Some of these metrics might not be visible until after the first successful connection by a proxy\.
- **Important**  
 These logs are intended for human consumption for troubleshooting purposes and not for programmatic access\. The format and content of the logs is subject to change\.   
 In particular, older logs don't contain any prefixes indicating the endpoint for each request\. In newer logs, each entry is prefixed with the name of the associated proxy endpoint\. This name can be the name that you specified for a user\-defined endpoint, or the special name `default` for requests using the default endpoint of a proxy\.


## Using RDS Proxy with Aurora global databases

- **Important**  
If the DB cluster is part of a global database with write forwarding turned on, reduce your proxy's `MaxConnectionsPercent` value by the quota that's allotted for write forwarding\. The write forwarding quota is set in the DB cluster parameter `aurora_fwd_writer_max_connections_pct`\. For information about write forwarding, see [Using write forwarding in an Amazon Aurora global database](aurora-global-database-write-forwarding.md)\.

