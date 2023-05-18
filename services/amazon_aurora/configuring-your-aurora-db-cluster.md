---
id: Configuring your Aurora DB cluster
title: Configuring your Aurora DB cluster
created: 1683841041000
updated: 1683841041000
---
# Configuring your Aurora DB cluster

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-aurora-user-guide.git)
{% endhint %}

## Creating a DB cluster

- **Important**  
Before you can create an Aurora DB cluster, you must complete the tasks in [Setting up your environment for Amazon Aurora](CHAP_SettingUp_Aurora.md)\.
- **Note**  
For this example, **Standard create** is enabled, and **Easy create** isn't enabled\. For information about creating an Aurora MySQL DB cluster with **Easy create** enabled, see [Getting started with Amazon Aurora](CHAP_GettingStartedAurora.md)\.
- **Note**  
Before you can create an Aurora DB cluster using the AWS CLI, you must fulfill the required prerequisites, such as creating a VPC and an RDS DB subnet group\. For more information, see [DB cluster prerequisites](#Aurora.CreateInstance.Prerequisites)\.
- **Note**  
Before you can create an Aurora DB cluster using the AWS CLI, you must fulfill the required prerequisites, such as creating a VPC and an RDS DB subnet group\. For more information, see [DB cluster prerequisites](#Aurora.CreateInstance.Prerequisites)\.
- **Note**  
Additional settings are available if you are creating an Aurora Serverless v1 DB cluster\. For information about these settings, see [Creating an Aurora Serverless v1 DB cluster](aurora-serverless.create.md)\. Also, some settings aren't available for Aurora Serverless v1 because of Aurora Serverless v1 limitations\. For more information, see [Limitations of Aurora Serverless v1](aurora-serverless.md#aurora-serverless.limitations)\.
- **Note**  
The AWS Management Console doesn't show these settings for Aurora DB clusters\.
- **Note**  
The AWS Management Console doesn't show these settings for Aurora DB instances\.


## Connecting to a DB cluster

- **Note**  
For Aurora Serverless DB clusters, you connect to the database endpoint rather than to the DB instance\. You can find the database endpoint for an Aurora Serverless DB cluster on the **Connectivity & security** tab of the AWS Management Console\. For more information, see [Using Amazon Aurora Serverless v1](aurora-serverless.md)\.
- **Note**  
For a helpful and detailed guide on connecting to an Amazon Aurora MySQL DB cluster, you can see the [Aurora connection management](https://d1.awsstatic.com/whitepapers/RDS/amazon-aurora-connection-management-handbook.pdf) handbook\.
- **Note**  
This procedure doesn't require installing the web server in the tutorial, but it does require installing MariaDB 10\.5\.
- **Note**  
To connect to the cluster endpoint using SSL, your client connection utility must support Subject Alternative Names \(SAN\)\. If your client connection utility doesn't support SAN, you can connect directly to the instances in your Aurora DB cluster\. For more information on Aurora endpoints, see [Amazon Aurora connection management](Aurora.Overview.Endpoints.md)\.

