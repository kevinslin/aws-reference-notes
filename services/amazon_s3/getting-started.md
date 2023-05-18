---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Step 1: Create a bucket

- **Note**  
You are not charged for creating a bucket\. You are charged only for storing objects in the bucket and for transferring objects in and out of the bucket\. The charges that you incur through following the examples in this guide are minimal \(less than $1\)\. For more information about storage charges, see [Amazon S3 pricing](http://aws.amazon.com/s3/pricing/)\.


## Step 3: Download an object

- **Note**  
You can only download one object at a time\.
Objects with key names ending with period\(s\) "\." downloaded using the Amazon S3 console will have the period\(s\) "\." removed from the key name of the downloaded object\. To download an object with the key name ending in period\(s\) "\." retained in the downloaded object, you must use the AWS Command Line Interface \(AWS CLI\), AWS SDKs, or REST API\. For AWS CLI, REST API, and AWS SDK information and examples, see [Downloading an object](https://docs.aws.amazon.com/AmazonS3/latest/userguide/download-objects.html)\.


## Access control

- **Important**  
If your bucket uses the bucket owner enforced setting for S3 Object Ownership, you must use policies to grant access to your bucket and the objects in it\. With the bucket owner enforced setting enabled, requests to set access control lists \(ACLs\) or update ACLs fail and return the `AccessControlListNotSupported` error code\. Requests to read ACLs are still supported\.

