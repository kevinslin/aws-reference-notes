---
id: Routing internet traffic to your AWS resources
title: Routing internet traffic to your AWS resources
created: 1683841041000
updated: 1683841041000
---
# Routing internet traffic to your AWS resources

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-route53-docs.git)
{% endhint %}

## Amazon API Gateway API

- **Note**  
Route 53 doesn't charge for alias queries to API Gateway APIs or other AWS resources\.


## Amazon CloudFront distribution

- **Note**  
You can route traffic to a CloudFront distribution only for public hosted zones\.
- **Note**  
Route 53 doesn't charge for alias queries to CloudFront distributions or other AWS resources\.
- **Note**  
Changes generally propagate to all Route 53 servers within 60 seconds\. When the changes propagate, you'll be able to route traffic to your CloudFront distribution by using the name of the alias record that you create in this procedure\. <a name="routing-to-cloudfront-distribution-procedure"></a>


## App Runner service

- **Important**  
Amazon Route 53 currently supports alias records for AWS App Runner services that are created after August 1, 2022\.
- **Note**  
Route 53 doesn't charge for alias queries to App Runner service or other AWS resources\.


## AWS Elastic Beanstalk environment

- **Note**  
These procedures assume that you're already using Route 53 as the DNS service for your domain\. If you're using another DNS service, see [Making Amazon Route 53 the DNS service for an existing domainMaking Route 53 the DNS service for an existing domain](MigratingDNS.md) for information about using Route 53 as the DNS service provider for your domain\.


## ELB load balancer

- **Note**  
Route 53 doesn't charge for alias queries to ELB load balancers or other AWS resources\.


## Amazon S3 bucket

- **Note**  
Route 53 doesn't charge for alias queries to S3 buckets or other AWS resources\.


## Amazon Virtual Private Cloud interface endpoint

- **Note**  
Route 53 doesn't charge for alias queries to interface endpoints or other AWS resources\.


## Amazon WorkMail

- **Note**  
You can route traffic to an Amazon WorkMail domain only for public hosted zones\.

