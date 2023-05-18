---
id: Using the AWS SDKs
title: Using the AWS SDKs
created: 1683841041000
updated: 1683841041000
---
# Using the AWS SDKs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-glacier-developer-guide.git)
{% endhint %}

## Using the AWS SDK for Java

- **Note**  
The AWS SDK for Java provides thread\-safe clients for accessing S3 Glacier\. As a best practice, your applications should create one client and reuse the client between threads\.
- **Note**  
The preceding code segment specifies `AccountID` when creating the request\. However, when using the AWS SDK for Java, the `AccountId` in the request is optional, and therefore all the low\-level examples in this guide don't set this value\. The `AccountId` is the AWS account ID\. This value must match the AWS account ID associated with the credentials used to sign the request\. You can specify either the AWS account ID or optionally a '\-', in which case S3 Glacier uses the AWS account ID associated with the credentials used to sign the request\. If you specify your Account ID, do not include hyphens in it\. When using AWS SDK for Java, if you don't provide the account ID, the library sets the account ID to '\-'\.
- **Note**  
The high\-level `ArchiveTransferManager` class can be constructed with an `AmazonGlacierClient` instance or an `AWSCredentials` instance\.


## Using the AWS SDK for .NET

- **Note**  
The low\-level API and high\-level API provide thread\-safe clients for accessing S3 Glacier\. As a best practice, your applications should create one client and reuse the client between threads\.
- **Note**  
The preceding code segment specifies `AccountId` when creating the request\. However, when using the AWS SDK for \.NET, the `AccountId` in the request is optional, and therefore all the low\-level examples in this guide don't set this value\. The `AccountId` is the AWS account ID\. This value must match the AWS account ID associated with the credentials used to sign the request\. You can specify either the AWS account ID or optionally a '\-', in which case S3 Glacier uses the AWS account ID associated with the credentials used to sign the request\. If you specify your Account ID, do not include hyphens in it\. When using AWS SDK for \.NET, if you don't provide the account ID, the library sets the account ID to '\-'\.
- **Note**  
The high\-level `ArchiveTransferManager` class still needs the low\-level `AmazonGlacierClient` client, which you can pass either explicitly or the `ArchiveTransferManager` creates the client\.

