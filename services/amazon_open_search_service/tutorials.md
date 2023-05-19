---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## Creating and searching for documents

- **Note**  
This tutorial uses a domain with open access\. For the highest level of security, we recommend that you put your domain inside a virtual private cloud \(VPC\)\.
- **Note**  
You don't provide anything after `_doc` in the URL, where the ID normally goes\. Because you’re creating a document with a generated ID, you don’t provide one yet\. That’s reserved for updates\.
- **Note**  
If you try to update a document that does not exist, OpenSearch Service creates the document\.


## Migrating to OpenSearch Service

- **Important**  
Snapshots are only forward\-compatible, and only by one major version\. For example, you can't restore a snapshot from an OpenSearch 1\.*x* cluster on an Elasticsearch 7\.*x* cluster, only an OpenSearch 1\.*x* or 2\.*x* cluster\. Minor version matters, too\. You can't restore a snapshot from a self\-managed 5\.3\.3 cluster on a 5\.3\.2 OpenSearch Service domain\. We recommend choosing the most recent version of OpenSearch or Elasticsearch that your snapshot supports\. For a table of compatible versions, see [Using a snapshot to migrate data](version-migration.md#snapshot-based-migration)\.


## Creating a search application

- **Note**  
Standard API Gateway and Lambda pricing applies, but within the limited usage of this tutorial, costs should be negligible\.
- **Important**  
If you have fine\-grained access control enabled for the domain, you also need to [map the role to a user](fgac.md#fgac-mapping) in OpenSearch Dashboards, otherwise you'll see permissions errors\.


## Visualizing support calls

- **Note**  
These commands use the `us-west-2` Region, but you can use any Region that Amazon Comprehend supports\. To learn more, see the [AWS General Reference](https://docs.aws.amazon.com/general/latest/gr/rande.html#comprehend_region)\.
- **Tip**  
[LibriVox](https://librivox.org/) has public domain audiobooks that you can use for testing\.

