---
id: Monitoring domains
title: Monitoring domains
created: 1683841041000
updated: 1683841041000
---
# Monitoring domains

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## Monitoring cluster metrics

- **Important**  
Different versions of Elasticsearch use different thread pools to process calls to the `_index` API\. Elasticsearch 1\.5 and 2\.3 use the index thread pool\. Elasticsearch 5\.*x*, 6\.0, and 6\.2 use the bulk thread pool\. OpenSearch and Elasticsearch 6\.3 and later use the write thread pool\. Currently, the OpenSearch Service console doesn't include a graph for the bulk thread pool\.  
Use `GET _cluster/settings?include_defaults=true` to check thread pool and queue sizes for your cluster\.


## Monitoring logs

- **Note**  
Error logs are available only for OpenSearch and Elasticsearch versions 5\.1 and later\. Slow logs are available for all OpenSearch and Elasticsearch versions\.
- **Important**  
CloudWatch Logs supports [10 resource policies per Region](https://docs.aws.amazon.com/AmazonCloudWatchLogs/latest/APIReference/API_PutResourcePolicy.html)\. If you plan to enable logs for several OpenSearch Service domains, you should create and reuse a broader policy that includes multiple log groups to avoid reaching this limit\. For steps on updating your policy, see [Enabling log publishing \(AWS CLI\)](#createdomain-configure-slow-logs-cli)\.
- **Important**  
CloudWatch Logs supports [10 resource policies per Region](https://docs.aws.amazon.com/AmazonCloudWatchLogs/latest/APIReference/API_PutResourcePolicy.html)\. If you plan to enable slow logs for several OpenSearch Service domains, you should create and reuse a broader policy that includes multiple log groups to avoid reaching this limit\.
- **Note**  
If you plan to enable multiple logs, we recommend publishing each to its own log group\. This separation makes the logs easier to scan\.


## Monitoring audit logs

- **Note**  
To enable audit logs, your user role must be mapped to the `security_manager` role, which gives you access to the OpenSearch `plugins/_security` REST API\. To learn more, see [Modifying the master user](fgac.md#fgac-forget)\.
- **Important**  
If you encounter an error while following these steps, see [Can't enable audit logs](handling-errors.md#troubleshooting-audit-logs-error) for troubleshooting information\.


## Monitoring with CloudTrail

- **Note**  
CloudTrail only captures calls to the [Configuration API](https://docs.aws.amazon.com/opensearch-service/latest/APIReference/Welcome.html), such as `CreateDomain` and `GetUpgradeStatus`\. CloudTrail doesn't capture calls to the [OpenSearch APIs](supported-operations.md), such as `_search` and `_bulk`\. For these calls, see [Monitoring audit logs in Amazon OpenSearch Service](audit-logs.md)\.

