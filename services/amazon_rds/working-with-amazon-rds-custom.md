---
id: Working with Amazon RDS Custom
title: Working with Amazon RDS Custom
created: 1683841041000
updated: 1683841041000
---
# Working with Amazon RDS Custom

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## RDS Custom security

- **Important**  
If your DB instance is a read replica and uses the `custom-oracle-ee-cdb` engine, two secrets exist with the suffix `db-resource-id-numeric-string`, one for the master user and the other for `RDSADMIN`, `SYS`, and `SYSTEM`\. To find the correct secret, run the following command on the host:

