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

