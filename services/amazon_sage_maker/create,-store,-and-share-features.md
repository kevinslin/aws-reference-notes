---
id: 'Create, Store, and Share Features'
title: 'Create, Store, and Share Features'
created: 1683841041000
updated: 1683841041000
---
# Create, Store, and Share Features

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-sagemaker-developer-guide.git)
{% endhint %}

## Find Features in Your Feature Groups

- **Important**  
Use the latest version of Amazon SageMaker Studio to make sure that you're using the most recent version of the search functionality\. For information on updating Studio, see [Shut down and Update SageMaker Studio](studio-tasks-update-studio.md)\.


## Find Feature Groups in Your Feature Store

- **Note**  
The feature groups that you're searching for must be within the same AWS account and AWS Region\.
- **Important**  
Use the latest version of Amazon SageMaker Studio to make sure that you're using the most recent version of the search functionality\. For information on updating Studio, see [Shut down and Update SageMaker Studio](studio-tasks-update-studio.md)\.


## Adding Searchable Metadata to Your Features

- **Note**  
 The role that you use must have the following managed policies attached to it: `AmazonS3FullAccess` and `AmazonSageMakerFeatureStoreAccess`\.


## Create a Dataset From Your Feature Groups

- **Important**  
Feature Store requires data to be registered in a AWS Glue data catalog\. By default, Feature Store automatically builds an AWS Glue data catalog when you create a feature group\.
- **Note**  
To make sure that your data is up to date, you can set up a AWS Glue crawler to run on a schedule\.  
 To set up a AWS Glue crawler, specify an IAM role that the crawler is using to access the offline store’s S3 buckets\. For more information, see [Create an IAM role](https://docs.aws.amazon.com/glue/latest/dg/create-an-iam-role.html)\.  
 For more information on how to use AWS Glue and Athena to build a training dataset for model training and inference, see [Create Feature Groups](feature-store-create-feature-group.md)\.


## Security and Access Control

- **Note**  
The key policy for the online store also works for the offline store, only when the `kms:ViaService` condition is not specified\.
- **Important**  
You can specify a AWS KMS encryption key to encrypt the Amazon S3 location used for your offline feature store when you create a feature group\. If AWS KMS encryption key is not specified, by default we encrypt all data at rest using AWS KMS key\. By defining your [bucket\-level key](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-key.html) for SSE, you can reduce AWS KMS requests costs by up to 99 percent\.


## Quotas, Naming Rules and Data Types

- **Note**  
Soft limits can be increased based on your needs\.

