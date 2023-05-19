---
id: Searching data
title: Searching data
created: 1683841041000
updated: 1683841041000
---
# Searching data

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## Custom packages

- **Tip**  
Dictionary files use Java heap space proportional to their size\. For example, a 2 GiB dictionary file might consume 2 GiB of heap space on a node\. If you use large files, ensure that your nodes have enough heap space to accommodate them\. [Monitor](managedomains-cloudwatchmetrics.md#managedomains-cloudwatchmetrics-cluster-metrics) the `JVMMemoryPressure` metric, and scale your cluster as necessary\.
- **Note**  
If you receive a "package not found" error when you run the script using the AWS CLI, it likely means Boto3 is using whichever Region is specified in \~/\.aws/config, which isn't the Region your S3 bucket is in\. Either run `aws configure` and specify the correct Region, or explicitly add the Region to the client:


## SQL support

- **Note**  
If your domain is running Elasticsearch rather than OpenSearch, the format is `_opendistro/_sql`\.


## Cross-cluster search

- **Note**  
If you include remote indexes in the path, you must URL\-encode the URI in the domain ARN\. For example, use `arn:aws:es:us-east-1:123456789012:domain/my-domain/local_index,dst%3Aremote_index` rather than `arn:aws:es:us-east-1:123456789012:domain/my-domain/local_index,dst:remote_index`\.
- **Note**  
All cross\-cluster search requests between domains are encrypted in transit by default as part of node\-to\-node encryption\.


## Learning to Rank

- **Note**  
To use the Learning to Rank plugin, you must have full admin permissions\. To learn more, see [Modifying the master user](fgac.md#fgac-forget)\.
- **Note**  
You must perform this step outside of OpenSearch Service\.
- **Note**  
You must perform this step outside of OpenSearch Service\.
- **Note**  
You must perform this step outside of OpenSearch Service\.


## Asynchronous search

- **Note**  
If you're using Elasticsearch 7\.10 instead of an OpenSearch version, replace `_plugins` with `_opendistro` in all asynchronous search requests\.
- **Note**  
All request parameters that apply to a standard `_search` query are supported\. If you're using Elasticsearch 7\.10 instead of an OpenSearch version, replace `_plugins` with `_opendistro`\.
- **Note**  
You can monitor asynchronous search statistics in CloudWatch\. For a full list of metrics, see [Asynchronous search metrics](managedomains-cloudwatchmetrics.md#managedomains-cloudwatchmetrics-asynchronous-search)\.


## Point in time

- **Note**  
You can monitor PIT search statistics in CloudWatch\. For a full list of metrics, see [Point in time metrics](managedomains-cloudwatchmetrics.md#managedomains-cloudwatchmetrics-pit)\.

