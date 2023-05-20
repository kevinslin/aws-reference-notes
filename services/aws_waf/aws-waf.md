---
id: AWS WAF
title: AWS WAF
created: 1683841041000
updated: 1683841041000
---
# AWS WAF

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-waf-and-shield-advanced-developer-guide.git)
{% endhint %}

## Getting started with AWS WAF

- **Note**  
AWS typically bills you less than US $0\.25 per day for the resources that you create during this tutorial\. When you're finished with the tutorial, we recommend that you delete the resources to prevent incurring unnecessary charges\.
- **Note**  
AWS typically bills you less than US $0\.25 per day for the resources that you create during this tutorial\. When you're finished, we recommend that you delete the resources to prevent incurring unnecessary charges\.


## Intelligent threat mitigation

- **Note**  
The features described here incur additional costs, beyond the basic fees for using AWS WAF\. For more information, see [AWS WAF Pricing](http://aws.amazon.com/waf/pricing/)\.


## How AWS WAF works with Amazon CloudFront features

- **Note**  
Responses that you customize using AWS WAF rules take precedence over any response specifications that you define in CloudFront custom error pages\.
- **Note**  
CloudFront can't distinguish between an HTTP status code 403 that is returned by your origin and one that is returned by AWS WAF when a request is blocked\. This means that you can't return different custom error pages based on the different causes of an HTTP status code 403\.


## Security in your use of the AWS WAF service

- **Note**  
This section provides standard AWS security guidance for your use of the AWS WAF service and its AWS resources, such as AWS WAF web ACLs and rule groups\.   
For information about protecting your AWS resources using AWS WAF, see the rest of the AWS WAF guide\.


## AWS WAF quotas

- **Note**  
This is the latest version of AWS WAF\. For AWS WAF Classic, see [AWS WAF Classic](classic-waf-chapter.md)\.

