---
id: Hosting a static website
title: Hosting a static website
created: 1683841041000
updated: 1683841041000
---
# Hosting a static website

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Website endpoints

- **Important**  
Amazon S3 website endpoints do not support HTTPS or access points\. If you want to use HTTPS, you can use Amazon CloudFront to serve a static website hosted on Amazon S3\. For more information, see [How do I use CloudFront to serve HTTPS requests for my Amazon S3 bucket?](https://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-https-requests-s3) To use HTTPS with a custom domain, see [Configuring a static website using a custom domain registered with Route 53](https://docs.aws.amazon.com/AmazonS3/latest/userguide/website-hosting-custom-domain-walkthrough.html)\.  
Requester Pays buckets  do not allow access through a website endpoint\. Any request to such a bucket receives a 403 Access Denied response\. For more information, see [Using Requester Pays buckets for storage transfers and usage](RequesterPaysBuckets.md)\.


## Configuring a custom error document

- **Note**  
Some browsers display their own error message when an error occurs, ignoring the error document that Amazon S3 returns\. For example, when an HTTP 404 Not Found error occurs, Google Chrome might ignore the error document that Amazon S3 returns and display its own error\.


## Setting permissions for website access

- **Note**  
On the website endpoint, if a user requests an object that doesn't exist, Amazon S3 returns HTTP response code `404 (Not Found)`\. If the object exists but you haven't granted read permission on it, the website endpoint returns HTTP response code `403 (Access Denied)`\. The user can use the response code to infer whether a specific object exists\. If you don't want this behavior, you should not enable website support for your bucket\.
- **Important**  
The following policy is an example only and allows full access to the contents of your bucket\. Before you proceed with this step, review [How can I secure the files in my Amazon S3 bucket?](https://aws.amazon.com/premiumsupport/knowledge-center/secure-s3-resources/) to ensure that you understand the best practices for securing the files in your S3 bucket and risks involved in granting public access\.
- **Important**  
If your bucket uses the bucket owner enforced setting for S3 Object Ownership, you must use policies to grant access to your bucket and the objects in it\. With the bucket owner enforced setting enabled, requests to set access control lists \(ACLs\) or update ACLs fail and return the `AccessControlListNotSupported` error code\. Requests to read ACLs are still supported\.


## Configuring a redirect

- **Important**  
To create redirection rules in the new Amazon S3 console, you must use JSON\. For JSON examples, see [Redirection rules examples](#redirect-rule-examples)\.
- **Important**  
To create redirection rules in the new Amazon S3 console, you must use JSON\.

