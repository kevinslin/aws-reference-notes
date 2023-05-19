---
id: Amazon OpenSearch Serverless
title: Amazon OpenSearch Serverless
created: 1683841041000
updated: 1683841041000
---
# Amazon OpenSearch Serverless

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## What is Amazon OpenSearch Serverless?

- **Note**  
Collections with unique AWS KMS keys can't share OCUs with other collections\.


## Managing capacity limits

- **Note**  
Although capacity can scale up to accomodate data, it can't currently scale up *search* replicas\. OpenSearch Serverless functions with two search replicas running in active\-active mode\. If you need more replicas for your workload, contact [AWS Support](https://console.aws.amazon.com/support/home)\.
- **Note**  
At this time, capacity settings only apply at the account level\. You can't configure per\-collection capacity limits\.


## Ingesting data into collections

- **Note**  
You must have version 2\.30\.0 or later of the AWS for Fluent Bit image in order to integrate with OpenSearch Serverless\.

