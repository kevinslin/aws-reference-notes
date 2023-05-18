---
id: Monitoring metrics in an Aurora DB cluster
title: Monitoring metrics in an Aurora DB cluster
created: 1683841041000
updated: 1683841041000
---
# Monitoring metrics in an Aurora DB cluster

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Viewing cluster status and recommendations

- **Note**  
Aurora also uses another status called *maintenance status*, which is shown in the **Maintenance** column of the Amazon RDS console\. This value indicates the status of any maintenance patches that need to be applied to a DB cluster\. Maintenance status is independent of DB cluster status\. For more information about maintenance status, see [Applying updates for a DB cluster](USER_UpgradeDBInstance.Maintenance.md#USER_UpgradeDBInstance.OSUpgrades)\.
- **Note**  
Amazon RDS also uses another status called *maintenance status*, which is shown in the **Maintenance** column of the Amazon RDS console\. This value indicates the status of any maintenance patches that need to be applied to a DB instance\. Maintenance status is independent of DB instance status\. For more information about maintenance status, see [Applying updates for a DB cluster](USER_UpgradeDBInstance.Maintenance.md#USER_UpgradeDBInstance.OSUpgrades)\.


## Analyzing performance with DevOps Guru for RDS

- **Important**  
We recommend that you test any changes on a test instance before modifying a production instance\. In this way, you understand the impact of the change\.

