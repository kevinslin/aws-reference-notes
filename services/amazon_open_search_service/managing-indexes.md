---
id: Managing indexes
title: Managing indexes
created: 1683841041000
updated: 1683841041000
---
# Managing indexes

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## UltraWarm storage

- **Note**  
The `ultrawarm_manager` role might not be defined on some preexisting OpenSearch Service domains\. If you don't see the role in Dashboards, you need to [manually create it](#ultrawarm-create-role)\.
- **Note**  
Domains support a maximum number of warm nodes\. For details, see [Amazon OpenSearch Service quotas](limits.md)\.


## Cold storage

- **Note**  
The `cold_manager` role might not exist on some preexisting OpenSearch Service domains\. If you don't see the role in Dashboards, you need to [manually create it](#coldstorage-create-role)\.
- **Note**  
An explicit `timestamp_field` is required in order to move indexes to cold storage using an Index State Management policy\.
- **Note**  
OpenSearch Dashboards doesn't support the PATCH method\. Use [curl](https://curl.haxx.se/), [Postman](https://www.getpostman.com/), or some other method to update cold metadata\.


## Index State Management

- **Important**  
You can no longer use index templates to apply ISM policies to newly created indexes\. You can continue to automatically manage newly created indexes with the [ISM template field](https://opensearch.org/docs/latest/im-plugin/ism/policies/#sample-policy-with-ism-template-for-auto-rollover)\. This update introduces a breaking change that affects existing CloudFormation templates using this setting\.
- **Note**  
If your domain is running a legacy Elasticsearch version, use `_opendistro` instead of `_plugins`\.


## Index rollups

- **Note**  
OpenSearch versions 2\.2 and later support searching multiple rollup indexes in one request\. OpenSearch versions prior to 2\.2 and legacy Elasticsearch OSS versions only support one rollup index per search\.


## Cross-cluster replication

- **Note**  
The commands to start replication and create a replication rule are special cases\. Because they invoke background processes on the leader and follower domains, you must pass a `leader_cluster_role` and `follower_cluster_role` in the request\. OpenSearch Service uses these roles in all backend replication tasks\. For information about mapping and using these roles, see [Map the leader and follower cluster roles](https://opensearch.org/docs/replication-plugin/permissions/#map-the-leader-and-follower-cluster-roles) in the OpenSearch documentation\.
- **Note**  
If you previously connected two domains to perform [cross\-cluster searches](cross-cluster-search.md), you can't use that same connection for replication\. The connection is marked as `SEARCH_ONLY` in the console\. In order to perform replication between two previously connected domains, you must delete the connection and recreate it\. When you've done this, the connection is available for both cross\-cluster search and cross\-cluster replication\.


## Data streams

- **Note**  
If you migrate a backing index to [cold storage](cold-storage.md), OpenSearch removes this index from the data stream\. Even if you move the index back to [UltraWarm](ultrawarm.md), the index remains independent and not part of the original data stream\. After an index has been removed from the data stream, searching against the stream won't return any data from the index\.

