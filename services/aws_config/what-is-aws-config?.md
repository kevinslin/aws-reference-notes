---
id: What Is AWS Config?
title: What Is AWS Config?
created: 1683841041000
updated: 1683841041000
---
# What Is AWS Config?

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-config-developer-guide.git)
{% endhint %}

## Concepts

- **Note**  
Aggregators provide a *read\-only view* into the source accounts and regions that the aggregator is authorized to view\. Aggregators do not provide mutating access into the source account or region\. For example, this means that you cannot deploy rules through an aggregator or pull snapshot files from the source account or region through an aggregator\.


## How AWS Config Works

- **Note**  
AWS Config only delivers the configuration history files and configuration snapshots to the specified S3 bucket; AWS Config doesn't modify the lifecycle policies for objects in the S3 bucket\. You can use lifecycle policies to specify whether you want to delete or archive objects to Amazon S3 Glacier\. For more information, see [Managing Lifecycle Configuration](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/LifecycleConfiguration.html) in the *Amazon Simple Storage Service User Guide*\. You can also see the [Archiving Amazon S3 Data to S3 Glacier](https://aws.amazon.com/blogs/aws/archive-s3-to-glacier/) blog post\.


## Supported Resource Types

- **Note**  
When AWS Config onboards new resource types, the default resources for the new resource types will be discovered during the account baselining process\. If you have the configuration recorder set up to record all supported resource types, you may receive notifications for default resources while a new resource type is in the process of onboarding\. The public documentation is updated once the onboarding process is complete\.
- **Note**  
On September 8, 2021, Amazon Elasticsearch Service was renamed to Amazon OpenSearch Service\. OpenSearch Service supports OpenSearch as well as legacy Elasticsearch OSS\. For more information, see [Amazon OpenSearch Service \- Summary of changes](https://docs.aws.amazon.com/opensearch-service/latest/developerguide/rename.html)\.  
You may continue to see your data for `AWS::OpenSearch::Domain` under the existing `AWS::Elasticsearch::Domain` resource type for several weeks, even if you upgrade one or more domains to OpenSearch\.
- **Note**  
Recording for the `AWS::Config::ConformancePackCompliance` and `AWS::Config::ConfigurationRecorder` resource types come with no additional charge\.


## Service Limits

- **Note**  
AWS Config rules in conformance packs count in the limit for the Maximum number of AWS Config Rules per Region per account\.
- **Note**  
Deploying at the organization level counts in the limit for child accounts\. AWS Config rules in conformance packs count in the limit for the Maximum number of AWS Config Rules per Region per account\.
- **Note**  
Deploying at the organization level counts in the limit for child accounts\.

