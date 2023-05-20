---
id: Multi-Account Multi-Region Data Aggregation
title: Multi-Account Multi-Region Data Aggregation
created: 1683841041000
updated: 1683841041000
---
# Multi-Account Multi-Region Data Aggregation

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-config-developer-guide.git)
{% endhint %}

## Setting Up an Aggregator (AWS CLI)

- **Note**  
Ensure that the management account registers a delegated administrator with both of the following AWS Config service principal names \(`config.amazonaws.com` and`config-multiaccountsetup.amazonaws.com`\) before the delegated administrator creates an aggregator\. To register a delegated administrator, see [Register a Delegated Administrator](#register-a-delegated-administrator-cli)\.
- **Note**  
Copy the Amazon Resource Name \(ARN\) from this IAM role for use when you create your AWS Config aggregator\. You can find the ARNallows on the response object\.


## Authorizing Aggregator Accounts (Console)

- **Note**  
**Authorization approval period**  
Authorization approval is required to add source accounts to an individual account aggregator\. A pending authorization approval request will be available for 7 days after an individual account aggregator adds a source account\.

