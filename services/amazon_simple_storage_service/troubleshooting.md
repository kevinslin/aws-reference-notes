---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Troubleshoot Access Denied (403 Forbidden) errors

- **Note**  
`Allow` statements in a bucket policy apply only to objects that are [owned by the same bucket\-owning account](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html)\. However, `Deny` statements in a bucket policy apply to all objects regardless of object ownership\.
- **Note**  
If you get locked out of a bucket because of an incorrect bucket policy, [sign in to the AWS Management Console by using your root user credentials\.](https://docs.aws.amazon.com/signin/latest/userguide/introduction-to-root-user-sign-in-tutorial.html) To regain access to your bucket, make sure to delete the bucket policy by using your root user credentials\.


## Troubleshoot lifecycle issues

- **Note**  
Amazon S3 doesn’t transition objects that are smaller than 128 KB from the S3 Standard or S3 Standard\-IA storage class to the S3 Intelligent\-Tiering, S3 Standard\-IA, or S3 One Zone\-IA storage class\.
- **Note**  
Amazon S3 rounds the transition or expiration date of an object to midnight UTC the next day\. For more information, see [Lifecycle rules: Based on an object's age](https://docs.aws.amazon.com/AmazonS3/latest/dev/intro-lifecycle-rules.html#intro-lifecycle-rules-number-of-days)\.
For S3 objects that are protected by Object Lock, current versions are not permanently deleted\. Instead, a delete marker is added to the objects, making them noncurrent\. Noncurrent versions are then preserved and are not permanently expired\.
- **Note**  
For S3 objects that are protected by Object Lock, current versions are not permanently deleted\. Instead, a delete marker is added to the objects, making them noncurrent\. Noncurrent versions are then preserved and are not permanently expired\.
- **Note**  
If the S3 bucket is protected by [AWS Backup](https://docs.aws.amazon.com/aws-backup/latest/devguide/s3-backups.html) or [S3 Replication](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication.html), you might also be able to use these features to recover your expired objects\.


## Troubleshoot replication

- **Note**  
If the destination bucket's object ownership settings include **Bucket owner enforced**, then you don't need to update the setting to **Change object ownership to the destination bucket owner** in the replication rule\. The object ownership change will occur by default\. For more information about changing replica ownership, see [Changing the replica owner](https://docs.aws.amazon.com/AmazonS3/latest/userguide/replication-change-owner.html)\.


## Troubleshoot server access logging

- **Note**  
We recommend that you choose a target bucket that's different from the source bucket\. When the source bucket and target bucket are the same, additional logs are created for the logs that are written to the bucket, which can increase your storage bill\. These extra logs about logs can also make it difficult to find the particular logs that you're looking for\. For simpler log management, we recommend saving access logs in a different bucket\. For more information, see [How do I enable log delivery?](ServerLogs.md#server-access-logging-overview)\.


## Troubleshoot versioning

- **Note**  
For S3 Object Lock\-enabled buckets, a `DELETE` object request with a protected object version ID causes a 403 Access Denied error\. A `DELETE` object request without a version ID adds a delete marker as the newest version of the object with a 200 OK response\. Objects protected by Object Lock cannot be permanently deleted until their retention periods and legal holds are removed\. For more information, see [How S3 Object Lock works](object-lock-overview.md)\.


## Get Amazon S3 request IDs for AWS Support

- **Note**  
HTTPS requests are encrypted and hidden in most packet captures\.
- **Note**  
By default, the returned log contains only error information\. To get the request IDs, the config file must have `AWSLogMetrics` \(and optionally, `AWSResponseLogging`\) added\.

