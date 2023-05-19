---
id: Best practices
title: Best practices
created: 1683841041000
updated: 1683841041000
---
# Best practices

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## Sizing domains

- **Tip**  
For a summary of the hardware resources that are allocated to each instance type, see [Amazon OpenSearch Service pricing](https://aws.amazon.com/opensearch-service/pricing/)\.


## Dedicated master nodes

- **Note**  
If your cluster doesn't have the necessary quorum to elect a new master node, write *and* read requests to the cluster both fail\. This behavior differs from the OpenSearch default\.


## Recommended CloudWatch alarms

- **Note**  
If you deploy the CloudFormation stack, the `KMSKeyError` and `KMSKeyInaccessible` alarms will exists in an `Insufficient Data` state because these metrics only appear if a domain encounters a problem with its encryption key\.
- **Note**  
If you just want to *view* metrics, see [Monitoring OpenSearch cluster metrics with Amazon CloudWatch](managedomains-cloudwatchmetrics.md)\.

