---
id: Managing storage
title: Managing storage
created: 1683841041000
updated: 1683841041000
---
# Managing storage

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Using S3 Versioning

- **Note**  
The SOAP API does not support S3 Versioning\. SOAP support over HTTP is deprecated, but it is still available over HTTPS\. New Amazon S3 features are not supported for SOAP\.
Normal Amazon S3 rates apply for every version of an object stored and transferred\. Each version of an object is the entire object; it is not just a diff from the previous version\. Thus, if you have three versions of an object stored, you are charged for three objects\.
- **Important**  
If you have an object expiration lifecycle configuration in your unversioned bucket and you want to maintain the same permanent delete behavior when you enable versioning, you must add a noncurrent expiration configuration\. The noncurrent expiration lifecycle configuration manages the deletes of the noncurrent object versions in the version\-enabled bucket\. \(A version\-enabled bucket maintains one current, and zero or more noncurrent, object versions\.\) For more information, see [Setting lifecycle configuration on a bucket](how-to-set-lifecycle-configuration-intro.md)\.


## Using AWS Backup for Amazon S3

- **Note**  
We recommend that you [ set a lifecycle expiration rule for versioning\-enabled buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/lifecycle-configuration-examples.html#lifecycle-config-conceptual-ex6) that are being backed up\. If you do not set a lifecycle expiration period, your Amazon S3 storage costs might increase because AWS Backup retains all versions of your Amazon S3 data\.


## Working with archived objects

- **Note**  
Unlike in the S3 Glacier Flexible Retrieval and S3 Glacier Deep Archive storage classes, restore requests for S3 Intelligent\-Tiering objects don't accept the `days` value\.
- **Note**  
When you restore an archive from S3 Glacier Flexible Retrieval or S3 Glacier Deep Archive, you pay for both the archived object and a copy that you restored temporarily\. For information about pricing, see [Amazon S3 pricing](https://aws.amazon.com/s3/pricing/)\.


## Managing storage classes

- **Note**  
Only activate the Archive Access tier for 90 days if you want to bypass the Archive Instant Access tier\. The Archive Access tier delivers slightly lower\-cost storage with minute\-to\-hour retrieval times\. The Archive Instant Access tier delivers millisecond access and high\-throughput performance\.
Activate the Archive Access and Deep Archive Access tiers only if your objects can be accessed asynchronously by your application\. If the object that you are retrieving is stored in the Archive Access or Deep Archive Access tiers, first restore the object by using `RestoreObject`\.
- **Note**  
If the size of an object is less than 128 KB, it is not monitored and not eligible for auto\-tiering\. Smaller objects are always stored in the Frequent Access tier\. For more information about S3 Intelligent\-Tiering, see [S3 Intelligent\-Tiering access tiers](intelligent-tiering-overview.md#intel-tiering-tier-definition)\.
- **Note**  
The S3 Standard\-IA and S3 One Zone\-IA storage classes are suitable for objects larger than 128 KB that you plan to store for at least 30 days\. If an object is less than 128 KB, Amazon S3 charges you for 128 KB\. If you delete an object before the end of the 30\-day minimum storage duration period, you are charged for 30 days\. For pricing information, see [Amazon S3 pricing](https://aws.amazon.com/s3/pricing/)\.
- **Important**  
When you choose the S3 Glacier Flexible Retrieval or S3 Glacier Deep Archive storage class, your objects remain in Amazon S3\. You can't access them directly through the separate Amazon S3 Glacier service\.
- **Note**  
S3 on Outposts doesn't support server\-side encryption with AWS Key Management Service \(AWS KMS\) keys \(SSE\-KMS\.


## Managing inventory

- **Important**  
Amazon S3 now applies server\-side encryption with Amazon S3 managed keys \(SSE\-S3\) as the base level of encryption for every bucket in Amazon S3\. Starting January 5, 2023, all new object uploads to Amazon S3 are automatically encrypted at no additional cost and with no impact on performance\. The automatic encryption status for S3 bucket default encryption configuration and for new object uploads is available in AWS CloudTrail logs, S3 Inventory, S3 Storage Lens, the Amazon S3 console, and as an additional Amazon S3 API response header in the AWS Command Line Interface and AWS SDKs\. For more information, see [Default encryption FAQ](https://docs.aws.amazon.com/AmazonS3/latest/userguide/default-encryption-faq.html)\.
- **Note**  
When an object reaches the end of its lifetime based on its lifecycle configuration, Amazon S3 queues the object for removal and removes it asynchronously\. Therefore, there might be a delay between the expiration date and the date when Amazon S3 removes an object\. The inventory report includes the objects that have expired but haven't been removed yet\. For more information about expiration actions in S3 Lifecycle, see [Expiring objects](lifecycle-expire-general-considerations.md)\.


## Replicating objects

- **Note**  
S3 RTC does not apply to Batch Replication\. Batch Replication is an on\-demand replication job, and can be tracked with S3 Batch Operations\. For more information, see [Tracking job status and completion reports](batch-ops-job-status.md)\.


## Using object tags

- **Important**  
It is acceptable to use tags to label objects containing confidential data, such as personally identifiable information \(PII\) or protected health information \(PHI\)\. However, the tags themselves shouldn't contain any confidential information\.

