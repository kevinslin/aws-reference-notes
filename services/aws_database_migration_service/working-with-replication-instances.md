---
id: Working with replication instances
title: Working with replication instances
created: 1683841041000
updated: 1683841041000
---
# Working with replication instances

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-dms-user-guide.git)
{% endhint %}

## Choosing replication instance types

- **Important**  
If you use a `dms.t3.micro` instance under the [AWS Free Tier](http://aws.amazon.com/free/) offer and use it in `unlimited` mode, charges might apply\. In particular, charges might apply if your average utilization over a rolling 24\-hour period exceeds the baseline utilization of the instance\. For more information, see [Baseline utilization](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/burstable-credits-baseline-concepts.html#baseline_performance) in the *Amazon EC2 User Guide for Linux Instances*\.  
T3 instances launch as `unlimited` by default\. If the average CPU usage over a 24\-hour period exceeds the baseline, you incur charges for surplus credits\. In some cases, you might launch T3 Spot Instances as `unlimited` and plan to use them immediately and for a short duration\. If you do so with no idle time for accruing CPU credits, you incur charges for surplus credits\. We recommend that you launch your T3 Spot Instances in standard mode to avoid paying higher costs\. For more information, see [Surplus credits can incur charges](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/burstable-performance-instances-unlimited-mode-concepts.html#unlimited-mode-surplus-credits), [T3 Spot Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-limits.html#t3-spot-instances), and [Standard mode for burstable performance instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/burstable-performance-instances-standard-mode.html) in the *Amazon EC2 User Guide for Linux Instances*\.


## Replication engine versions

- **Note**  
We recommend that you stop all tasks before upgrading the Replication Instance\. If you don't stop the task, AWS DMS will stop the task automatically before the upgrade\. If you stop the task manually, you will need to start the task manually after the upgrade is complete\. Upgrading the replication instance takes several minutes\. When the instance is ready, its status changes to **available**\.
- **Note**  
Upgrading the replication instance takes several minutes\. You can view the replication instance status using the following command\.


## Setting up a network for a replication instance

- **Note**  
Since an IP address can change as a result of changes to underlying infrastructure, we recommend you use a VPC CIDR range, or route your replication instance outbound traffic through a NAT GW associated Elastic IP\. For more information about creating a VPC, including a CIDR block, see [Work with VPCs and subnets](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html) in the *Amazon Virtual Private Cloud User Guide*\. For more information about Elastic IP addresses, see [Elastic IP addresses](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/elastic-ip-addresses-eip.html) in the *Amazon Elastic Compute Cloud User Guide*\.


## Modifying a replication instance

- **Note**  
If you choose to apply changes immediately, any changes in the pending modifications queue are also applied\. If any of the pending modifications require downtime, choosing **Apply changes immediately** can cause unexpected downtime\.


## Rebooting a replication instance

- **Note**  
After a reboot forces a failover from one Availability Zone to another, the Availability Zone change might not be reflected for several minutes\. This lag appears in the AWS Management Console, and in calls to the AWS CLI and AWS DMS API\.

