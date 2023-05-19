---
id: Uploading and Indexing Data
title: Uploading and Indexing Data
created: 1683841041000
updated: 1683841041000
---
# Uploading and Indexing Data

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cloudsearch-developer-guide.git)
{% endhint %}

## Uploading Data

- **Important**  
Before uploading data to an Amazon CloudSearch domain, follow these guidelines:  
Group documents into *batches* before you upload them\. Continuously uploading batches that consist of only one document has a huge, negative impact on the speed at which Amazon CloudSearch can process your updates\. Instead, create batches that are as close to the limit as possible and upload them less frequently\. For more information on maximum batch size and upload frequency, see [Understanding Amazon CloudSearch Limits](limits.md)\.
A domain's document and search endpoints remain the same for the life of the domain\. You should cache the endpoints rather than retrieving them before every upload or search request\. Querying the Amazon CloudSearch configuration service by calling `aws cloudsearch describe-domains` or `DescribeDomains` before every request will likely result in your requests being throttled\.
- **Note**  
To upload data from Amazon S3 or DynamoDB, you must have permission to access both the service and the resources you want to upload\. For more information, see [Using Bucket Policies and User Policies](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingIAMPolicies.html) and [Using IAM to Control Access to DynamoDB Resources](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/UsingIAMWithDDB.html)\.


## Indexing Document Data

- **Important**  
If you change the type of a field and have documents in your index that contain data that is incompatible with the new field type, all fields being processed are put in the `FailedToValidate` state when you run indexing and the indexing operation fails\. Rolling back the incompatible configuration change will enable you to successfully rebuild your index\. If the change is necessary, you must update or remove the incompatible documents from your index to use the new configuration\.
- **Note**  
Depending on the volume of data, building a full index can take a considerable amount of compute power\. Amazon CloudSearch automatically manages the resources needed to build the index in a timely fashion\. Most data updates and simple domain configuration changes are built and deployed in minutes\. Indexing large volumes of data and applying configuration changes that require rebuilding the full index will take longer to complete\.

