---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Transforming data with S3 Object Lambda

- **Note**  
For simplicity, this tutorial creates and uses an IAM user\. After completing this tutorial, remember to [Delete the IAM user](#ol-upper-step8-delete-user)\. For production use, we recommend that you follow the [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) in the *IAM User Guide*\. A best practice requires human users to use federation with an identity provider to access AWS with temporary credentials\. Another best practice is to require workloads to use temporary credentials with IAM roles to access AWS\. To learn about using AWS IAM Identity Center \(successor to AWS Single Sign\-On\) to create users with temporary credentials, see [Getting started](https://docs.aws.amazon.com/singlesignon/latest/userguide/getting-started.html) in the *AWS IAM Identity Center \(successor to AWS Single Sign\-On\) User Guide*\.   
This tutorial also uses full\-access AWS managed policies\. For production use, we recommend that you instead grant only the minimum permissions necessary for your use case, in accordance with [security best practices](security-best-practices.md#security-best-practices-prevent)\.
- **Note**  
The preceding example Lambda function loads the entire requested object into memory before transforming it and returning it to the client\. Alternatively, you can stream the object from S3 to avoid loading the entire object into memory\. This approach can be useful when working with large objects\. For more information about streaming responses with Object Lambda Access Points, see the streaming examples in [Working with `GetObject` requests in Lambda](olap-writing-lambda.md#olap-getobject-response)\.


## Detecting and redacting PII data

- **Note**  
For simplicity, this tutorial creates and uses an IAM user\. After completing this tutorial, remember to [Delete the IAM user](#ol-pii-step8-delete-user)\. For production use, we recommend that you follow the [Security best practices in IAM](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html) in the *IAM User Guide*\. A best practice requires human users to use federation with an identity provider to access AWS with temporary credentials\. Another best practice is to require workloads to use temporary credentials with IAM roles to access AWS\. To learn about using AWS IAM Identity Center \(successor to AWS Single Sign\-On\) to create users with temporary credentials, see [Getting started](https://docs.aws.amazon.com/singlesignon/latest/userguide/getting-started.html) in the *AWS IAM Identity Center \(successor to AWS Single Sign\-On\) User Guide*\.   
This tutorial also uses full\-access policies\. For production use, we recommend that you instead grant only the minimum permissions necessary for your use case, in accordance with [security best practices](security-best-practices.md#security-best-practices-prevent)\.


## Hosting video streaming

- **Note**  
When you register a domain, it costs money immediately and it's irreversible\. You can choose not to auto\-renew the domain, but you pay up front and own it for the year\. For more information, see [Registering a new domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html) in the *Amazon Route 53 Developer Guide*\.
- **Note**  
When you register a domain, it costs money immediately and it's irreversible\. You can choose not to auto\-renew the domain, but you pay up front and own it for the year\. For more information, see [Registering a new domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html) in the *Amazon Route 53 Developer Guide*\.
- **Important**  
If you want to transfer the domain between AWS accounts or transfer the domain to another registrar, don't delete the domain and expect to immediately reregister it\. Instead, see the applicable documentation in the *Amazon Route 53 Developer Guide*:  
[Transferring a domain to a different AWS account](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-between-aws-accounts.html)
[Transferring a domain from Amazon Route 53 to another registrar](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-from-route-53.html)


## Batch-transcoding videos

- **Note**  
Before you start creating an S3 Batch Operations job, make sure that the **Create job from manifest** button is enabled\. For more information, see [Check the inventory report for your S3 video source bucket](#batchops-s3-step5-manifest)\. If the **Create job from manifest** button is disabled, the first inventory report has not been delivered and you must wait until the button is enabled\. After you configure Amazon S3 Inventory for your S3 source bucket in [Step 5](#batchops-s3-step5), it can take up to 48 hours to deliver the first inventory report\.


## Configuring a static website

- **Important**  
Amazon S3 now applies server\-side encryption with Amazon S3 managed keys \(SSE\-S3\) as the base level of encryption for every bucket in Amazon S3\. Starting January 5, 2023, all new object uploads to Amazon S3 are automatically encrypted at no additional cost and with no impact on performance\. The automatic encryption status for S3 bucket default encryption configuration and for new object uploads is available in AWS CloudTrail logs, S3 Inventory, S3 Storage Lens, the Amazon S3 console, and as an additional Amazon S3 API response header in the AWS Command Line Interface and AWS SDKs\. For more information, see [Default encryption FAQ](https://docs.aws.amazon.com/AmazonS3/latest/userguide/default-encryption-faq.html)\.
- **Important**  
The following policy is an example only and allows full access to the contents of your bucket\. Before you proceed with this step, review [How can I secure the files in my Amazon S3 bucket?](https://aws.amazon.com/premiumsupport/knowledge-center/secure-s3-resources/) to ensure that you understand the best practices for securing the files in your S3 bucket and risks involved in granting public access\.
- **Note**  
Amazon S3 does not support HTTPS access to the website\. If you want to use HTTPS, you can use Amazon CloudFront to serve a static website hosted on Amazon S3\.  
For more information, see [How do I use CloudFront to serve a static website hosted on Amazon S3?](http://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/) and [Requiring HTTPS for communication between viewers and CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/using-https-viewers-to-cloudfront.html)\.


## Configuring a static website using a custom domain

- **Note**  
Amazon S3 website endpoints do not support HTTPS or access points\. If you want to use HTTPS, you can use Amazon CloudFront to serve a static website hosted on Amazon S3\.  
For more information, see [How do I use CloudFront to serve a static website hosted on Amazon S3?](http://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/) and [Requiring HTTPS for communication between viewers and CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/using-https-viewers-to-cloudfront.html)\.
- **Important**  
The following policy is an example only and allows full access to the contents of your bucket\. Before you proceed with this step, review [How can I secure the files in my Amazon S3 bucket?](https://aws.amazon.com/premiumsupport/knowledge-center/secure-s3-resources/) to ensure that you understand the best practices for securing the files in your S3 bucket and risks involved in granting public access\.
- **Note**  
Amazon S3 does not support HTTPS access to the website\. If you want to use HTTPS, you can use Amazon CloudFront to serve a static website hosted on Amazon S3\.  
For more information, see [How do I use CloudFront to serve a static website hosted on Amazon S3?](http://aws.amazon.com/premiumsupport/knowledge-center/cloudfront-serve-static-website/) and [Requiring HTTPS for communication between viewers and CloudFront](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/using-https-viewers-to-cloudfront.html)\.
- **Note**  
Changes generally propagate to all Route 53 servers within 60 seconds\. When propagation is done, you can route traffic to your Amazon S3 bucket by using the names of the alias records that you created in this procedure\.
- **Note**  
Changes generally propagate to all Route 53 servers within 60 seconds\. When propagation is done, you can route traffic to your Amazon S3 bucket by using the names of the alias records that you created in this procedure\.

