---
id: Working with buckets
title: Working with buckets
created: 1683841041000
updated: 1683841041000
---
# Working with buckets

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Buckets overview

- **Note**  
Objects that belong to a bucket that you create in a specific AWS Region never leave that Region, unless you explicitly transfer them to another Region\. For example, objects that are stored in the Europe \(Ireland\) Region never leave it\.
- **Note**  
If you see an `Error` when you list your buckets and their public access settings, you might not have the required permissions\. Make sure that you have the following permissions added to your user or role policy:
- **Note**  
There are also object\-level configurations\. For example, you can configure object\-level permissions by configuring an access control list \(ACL\) specific to that object\.


## Naming rules

- **Note**  
Before March 1, 2018, buckets created in the US East \(N\. Virginia\) Region could have names that were up to 255 characters long and included uppercase letters and underscores\. Beginning March 1, 2018, new buckets in US East \(N\. Virginia\) must conform to the same rules applied in all other Regions\.


## Methods for accessing a bucket

- **Note**  
Virtual\-hosted\-style and path\-style requests use the S3 dot Region endpoint structure \(`s3.Region`\), for example, `https://my-bucket.s3.us-west-2.amazonaws.com`\. However, some older Amazon S3 Regions also support S3 dash Region endpoints `s3-Region`, for example, `https://my-bucket.s3-us-west-2.amazonaws.com`\. If your bucket is in one of these Regions, you might see `s3-Region` endpoints in your server access logs or AWS CloudTrail logs\. We recommend that you do not use this endpoint structure in your requests\.
- **Important**  
Update \(September 23, 2020\) – To make sure that customers have the time that they need to transition to virtual\-hosted–style URLs, we have decided to delay the deprecation of path\-style URLs\. For more information, see [Amazon S3 Path Deprecation Plan – The Rest of the Story](https://aws.amazon.com/blogs/aws/amazon-s3-path-deprecation-plan-the-rest-of-the-story/) in the *AWS News Blog*\.
- **Note**  
If your access point name includes dash \(\-\) characters, include the dashes in the URL and insert another dash before the account ID\. For example, to use an access point named `finance-docs` owned by account `123456789012` in Region `us-west-2`, the appropriate URL would be `https://finance-docs-123456789012.s3-accesspoint.us-west-2.amazonaws.com`\.
S3 access points don't support access by HTTP, only secure access by HTTPS\.


## Emptying a bucket

- **Note**  
You can't remove objects from a bucket that has versioning enabled\. Amazon S3 adds a delete marker when you delete an object, which is what this command does\. For more information about S3 Bucket Versioning, see [Using versioning in S3 buckets](Versioning.md)\.


## Deleting a bucket

- **Important**  
Bucket names are unique\. If you delete a bucket, another AWS user can use the name\. If you want to continue to use the same bucket name, don't delete the bucket\. We recommend that you empty the bucket and keep it\.
- **Note**  
For buckets without versioning enabled, you can delete all objects directly and then delete the bucket\. For buckets with versioning enabled, you must delete all object versions before deleting the bucket\.


## Setting default bucket encryption

- **Important**  
Amazon S3 now applies server\-side encryption with Amazon S3 managed keys \(SSE\-S3\) as the base level of encryption for every bucket in Amazon S3\. Starting January 5, 2023, all new object uploads to Amazon S3 are automatically encrypted at no additional cost and with no impact on performance\. The automatic encryption status for S3 bucket default encryption configuration and for new object uploads is available in AWS CloudTrail logs, S3 Inventory, S3 Storage Lens, the Amazon S3 console, and as an additional Amazon S3 API response header in the AWS Command Line Interface and AWS SDKs\. For more information, see [Default encryption FAQ](https://docs.aws.amazon.com/AmazonS3/latest/userguide/default-encryption-faq.html)\.
- **Note**  
We've changed buckets to encrypt new object uploads automatically\. If you previously created a bucket without default encryption, Amazon S3 will enable encryption by default for the bucket using SSE\-S3\. There will be no changes to the default encryption configuration for an existing bucket that already has SSE\-S3 or SSE\-KMS configured\. If you want to encrypt your objects with SSE\-KMS, you must change the encryption type in your bucket settings\. For more information, see [Protecting data using server\-side encryption with AWS Key Management Service keys \(SSE\-KMS\)](UsingKMSEncryption.md)\.
- **Note**  
Amazon S3 buckets with default bucket encryption using SSE\-KMS cannot be used as destination buckets for [Logging requests using server access logging](ServerLogs.md)\. Only SSE\-S3 default encryption is supported for server access log destination buckets\.


## Using Requester Pays

- **Important**  
If you enable Requester Pays on a bucket, anonymous access to that bucket is not allowed\.

