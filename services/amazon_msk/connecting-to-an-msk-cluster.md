---
id: Connecting to an MSK cluster
title: Connecting to an MSK cluster
created: 1683841041000
updated: 1683841041000
---
# Connecting to an MSK cluster

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-msk-developer-guide.git)
{% endhint %}

## Public access

- **Important**  
In addition to turning on public access, ensure that the cluster's security groups have inbound TCP rules that allow public access from your IP address\. We recommend that you make these rules as restrictive as possible\. For information about security groups and inbound rules, see [Security groups for your VPC](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) in the Amazon VPC User Guide\. For port numbers, see [Port information](port-info.md)\. For instructions on how to change a cluster's security group, see [Changing an Amazon MSK cluster's security group](change-security-group.md)\.
- **Note**  
If you use the following instructions to turn on public access and then still cannot access the cluster, see [Unable to access cluster that has public access turned on](troubleshooting.md#public-access-issues)\.
- **Note**  
To turn off public access, use a similar AWS CLI command, but with the following connectivity info instead:
- **Note**  
For security reasons, Amazon MSK doesn't allow public access to Apache ZooKeeper nodes\. For information about how to control access to the Apache ZooKeeper nodes of your MSK cluster from within AWS, see [Controlling access to Apache ZooKeeper](zookeeper-security.md)\.

