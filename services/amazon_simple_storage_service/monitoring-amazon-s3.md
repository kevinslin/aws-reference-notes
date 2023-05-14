---
id: Monitoring Amazon S3
title: Monitoring Amazon S3
created: 1683841041000
updated: 1683841041000
---
# Monitoring Amazon S3

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Logging with CloudTrail

- **Note**  
S3 does not support delivery of CloudTrail logs to the requester or the bucket owner for VPC endpoint requests when the VPC endpoint policy denies them\.
- **Important**  
Newer Amazon S3 features are not supported for SOAP\. We recommend that you use either the REST API or the AWS SDKs\.


## Logging server access

- **Note**  
Server access logs don't record information about wrong\-region redirect errors for Regions that launched after March 20, 2019\. Wrong\-region redirect errors occur when a request for an object or bucket is made outside the Region in which the bucket exists\.
- **Note**  
Amazon S3 does not support delivery of server access logs to the requester or the bucket owner for VPC endpoint requests when the VPC endpoint policy denies them\.


## Amazon S3 Event Notifications

- **Important**  
Amazon S3 event notifications are designed to be delivered at least once\. Typically, event notifications are delivered in seconds but can sometimes take a minute or longer\.
- **Note**  
Amazon Simple Queue Service FIFO \(First\-In\-First\-Out\) queues aren't supported as an Amazon S3 event notification destination\. To send a notification for an Amazon S3 event to an Amazon SQS FIFO queue, you can use Amazon EventBridge\. For more information, see [Enabling Amazon EventBridge](enable-event-notifications-eventbridge.md)\.

