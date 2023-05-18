---
id: Using RDS Proxy
title: Using RDS Proxy
created: 1683841041000
updated: 1683841041000
---
# Using RDS Proxy

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## RDS Proxy concepts and terminology

- **Note**  
 RDS Proxy uses certificates from the AWS Certificate Manager \(ACM\)\. If you are using RDS Proxy, you don't need to download Amazon RDS certificates or update applications that use RDS Proxy connections\.


## Getting started with RDS Proxy

- **Note**  
RDS Proxy never uses more than 215 IP addresses in a VPC\.
- **Note**  
For RDS for SQL Server, the number of Secrets Manager secrets that you need to create for a proxy depends on the collation that your DB instance uses\. For example, suppose that your DB instance uses case\-sensitive collation\. If your application accepts both "Admin" and "admin," then your proxy needs two separate secrets\. For more information about collation in SQL Server, see the [ Microsoft SQL Server](https://docs.microsoft.com/en-us/sql/relational-databases/collations/collation-and-unicode-support?view=sql-server-ver16) documentation\.
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
- **Note**  
RDS Proxy closes database connections some time after 24 hours when they are no longer in use\. The proxy performs this action regardless of the value of the maximum idle connections setting\.


## Working with RDS Proxy endpoints

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

