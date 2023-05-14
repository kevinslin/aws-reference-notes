---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Data encryption

- **Important**  
Amazon S3 now applies server\-side encryption with Amazon S3 managed keys \(SSE\-S3\) as the base level of encryption for every bucket in Amazon S3\. Starting January 5, 2023, all new object uploads to Amazon S3 are automatically encrypted at no additional cost and with no impact on performance\. The automatic encryption status for S3 bucket default encryption configuration and for new object uploads is available in AWS CloudTrail logs, S3 Inventory, S3 Storage Lens, the Amazon S3 console, and as an additional Amazon S3 API response header in the AWS Command Line Interface and AWS SDKs\. For more information, see [Default encryption FAQ](https://docs.aws.amazon.com/AmazonS3/latest/userguide/default-encryption-faq.html)\.


## AWS PrivateLink for Amazon S3

- **Important**  
To take advantage of the lowest cost network path when using **Enable private DNS only for inbound endpoints**, a gateway endpoint must be present in your VPC\. The presence of a gateway endpoint helps ensure that in\-VPC traffic always routes over the AWS private network when the **Enable private DNS only for inbound endpoints** option is selected\. You must maintain this gateway endpoint while you have the **Enable private DNS only for inbound endpoints** option selected\. If you want to delete your gateway endpoint you must first clear **Enable private DNS only for inbound endpoints**\.   
If you want to update an existing interface endpoint to **Enable private DNS only for inbound endpoints**, first confirm that your VPC has an S3 gateway endpoint\. For more information about gateway endpoints and managing private DNS names, see [Gateway VPC endpoints](https://docs.aws.amazon.com/vpc/latest/privatelink/vpce-gateway.html) and [Manage DNS names](https://docs.aws.amazon.com/vpc/latest/privatelink/manage-dns-names.html) respectively in the *AWS PrivateLink Guide*\.
- **Note**  
To specify the AWS account ID of the resource being accessed, you can use either the `aws:ResourceAccount` or the `s3:ResourceAccount` key in your IAM policy\. However, be aware that some AWS services rely on access to AWS managed buckets\. Therefore, using the `aws:ResourceAccount` or `s3:ResourceAccount` key in your IAM policy might also affect access to these resources\.
- **Important**  
When applying the following Amazon S3 bucket policy to restrict access to only certain VPC endpoints, you might block your access to the bucket without intending to do so\. Bucket policies that are intended to specifically limit bucket access to connections originating from your VPC endpoint can block all connections to the bucket\. For information about how to fix this issue, see [My bucket policy has the wrong VPC or VPC endpoint ID\. How can I fix the policy so that I can access the bucket?](https://aws.amazon.com/premiumsupport/knowledge-center/s3-regain-access/) in the *AWS Support Knowledge Center*\.
Before using the following example policy, replace the VPC endpoint ID with an appropriate value for your use case\. Otherwise, you won't be able to access your bucket\. 
This policy disables *console* access to the specified bucket, because console requests don't originate from the specified VPC endpoint\.


## Controlling object ownership

- **Note**  
If other AWS accounts need access to objects after uploading, you must grant additional permissions to those accounts through bucket policies\. For more information, see [Example walkthroughs: Managing access to your Amazon S3 resources](example-walkthroughs-managing-access.md)\.

