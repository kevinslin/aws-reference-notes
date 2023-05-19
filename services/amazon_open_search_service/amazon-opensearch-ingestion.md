---
id: Amazon OpenSearch Ingestion
title: Amazon OpenSearch Ingestion
created: 1683841041000
updated: 1683841041000
---
# Amazon OpenSearch Ingestion

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## Setting up roles and users

- **Note**  
The S3 access role that you specify must be the same as the [pipeline role]()\. Therefore, your pipeline role must contain two separate permissions policies—one to write to a sink, and one to pull from the S3 source\. You must use the same `sts_role_arn` in all pipeline components\.


## Getting started with OpenSearch Ingestion

- **Note**  
Pipeline creation will fail if you don't set up the correct permissions\. See [Setting up roles and users in Amazon OpenSearch Ingestion](pipeline-security-overview.md) for a better understanding of the required roles before you create a pipeline\.


## Pipeline features overview

- **Note**  
This is not an exhaustive list of features that are available for pipelines\. For comprehensive documentation of all available pipeline functionality, see the [Data Prepper documentation](https://opensearch.org/docs/latest/data-prepper/pipelines/pipelines/)\. Note that OpenSearch Ingestion places some constraints on the plugins and options that you can use\. For more information, see [Supported plugins and options for Amazon OpenSearch Ingestion pipelines](pipeline-config-reference.md)\.


## Creating pipelines

- **Note**  
If you're writing to a domain that uses fine\-grained access control, there are extra steps you need to complete\. See [Fine\-grained access control](pipeline-domain-access.md#pipeline-access-domain-fgac)\.
- **Note**  
In addition, the first user to create a pipeline in an account must have permissions for the `iam:CreateServiceLinkedRole` action\. For more information, see [pipeline role resource](pipeline-security.md#pipeline-vpc-slr)\.
- **Note**  
OpenSearch Ingestion doesn't immediately support new versions of Data Prepper as soon as they're released\. There will be some lag between when a new version is publicly available and when it's supported in OpenSearch Ingestion\. In addition, OpenSearch Ingestion might explicitly not support certain major or minor versions altogether\. For a comprehensive list, see [Supported Data Prepper versions](ingestion.md#ingestion-supported-versions)\.
- **Note**  
If you specify multiple sinks within a YAML pipeline definition, they must all be the *same* OpenSearch Service domain\. An OpenSearch Ingestion pipeline can't write to multiple different domains\.


## Supported plugins and options

- **Note**  
OpenSearch Ingestion doesn't support any buffer plugins because it automatically configures a default buffer\. You receive a validation error if you include a buffer in your pipeline configuration\.
- **Note**  
OpenSearch Ingestion doesn't support any buffer plugins because it automatically configures a default buffer\. You receive a validation error if you include a buffer in your pipeline configuration\.


## Sending data to pipelines

- **Note**  
To use the role for *all* pipelines, replace the ARN in the `Resource` element with a wildcard \(\*\)\.
- **Note**  
You can only provide cross\-account ingestion access for public pipelines, not VPC pipelines\.

