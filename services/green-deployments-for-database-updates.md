---
id: Using Blue/Green Deployments for database updates
title: Using Blue/Green Deployments for database updates
created: 1683841041000
updated: 1683841041000
---
# Using Blue/Green Deployments for database updates

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rds-user-guide.git)
{% endhint %}

## Overview of Amazon RDS Blue/Green Deployments

- **Note**  
Currently, blue/green deployments are supported only for RDS for MariaDB and RDS for MySQL\. For Amazon Aurora availabilty, see [Using Amazon RDS Blue/Green Deployments for database updates](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/blue-green-deployments.html) in the *Amazon Aurora User Guide*\.


## Creating a blue/green deployment

- **Important**  
If you switch over a blue/green deployment before data loading is complete, your application could experience performance issues due to high latency\.


## Switching a blue/green deployment

- **Note**  
During a switchover, you can't modify any DB instances included in the switchover\.


## Deleting a blue/green deployment

- **Important**  
Deleting a blue/green deployment doesn't affect the blue environment\.

