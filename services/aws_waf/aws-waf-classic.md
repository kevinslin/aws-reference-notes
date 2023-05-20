---
id: AWS WAF Classic
title: AWS WAF Classic
created: 1683841041000
updated: 1683841041000
---
# AWS WAF Classic

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-waf-and-shield-advanced-developer-guide.git)
{% endhint %}

## Setting up AWS WAF Classic

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.
- **Note**  
If you're a new user to AWS WAF, don't follow these setup steps for AWS WAF Classic\. Instead, follow the steps for the latest version of AWS WAF, at [Setting up](setting-up-waf.md)\.
- **Note**  
AWS Shield Standard is included with AWS WAF Classic and does not require additional setup\. For more information, see [How AWS Shield works](ddos-overview.md)\.


## How AWS WAF Classic works

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.
- **Note**  
You can also use AWS WAF Classic to protect your applications that are hosted in Amazon Elastic Container Service \(Amazon ECS\) containers\. Amazon ECS is a highly scalable, fast container management service that makes it easy to run, stop, and manage Docker containers on a cluster\. To use this option, you configure Amazon ECS to use an AWS WAF Classic enabled Application Load Balancer to route and protect HTTP/HTTPS \(layer 7\) traffic across the tasks in your service\. For more information, see the topic [Service Load Balancing](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-load-balancing.html) in the *Amazon Elastic Container Service Developer Guide*\.


## AWS WAF Classic pricing

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.


## Getting started with AWS WAF Classic

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.
- **Note**  
AWS typically bills you less than US $0\.25 per day for the resources that you create during this tutorial\. When you're finished with the tutorial, we recommend that you delete the resources to prevent incurring unnecessary charges\.
- **Note**  
For more information about IP match conditions, see [Working with IP match conditions](classic-web-acl-ip-conditions.md)\.<a name="classic-getting-started-wizard-create-ip-condition-procedure"></a>
- **Note**  
For more information about geo match conditions, see [Working with geographic match conditions](classic-web-acl-geo-conditions.md)\.<a name="classic-getting-started-wizard-create-geo-condition-procedure"></a>
- **Note**  
For more information about string match conditions, see [Working with string match conditions](classic-web-acl-string-conditions.md)\.<a name="classic-getting-started-wizard-create-string-condition-procedure"></a>
- **Note**  
For more information about regex match conditions, see [Working with regex match conditions](classic-web-acl-regex-conditions.md)\.<a name="classic-getting-started-wizard-create-regex-condition-procedure"></a>
- **Note**  
For more information about string match conditions, see [Working with SQL injection match conditions](classic-web-acl-sql-conditions.md)\.<a name="classic-getting-started-wizard-create-sql-condition-procedure"></a>
- **Note**  
For more information about rules, see [Working with rules](classic-web-acl-rules.md)\.<a name="classic-getting-started-wizard-create-rule-procedure"></a>
- **Note**  
AWS typically bills you less than US $0\.25 per day for the resources that you create during this tutorial\. When you're finished, we recommend that you delete the resources to prevent incurring unnecessary charges\. <a name="classic-getting-started-wizard-clean-up-procedure"></a>


## Creating and configuring a Web Access Control List (Web ACL)

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.


## Working with AWS WAF Classic rule groups for use with AWS Firewall Manager

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.
- **Important**  
If you want to add an AWS Marketplace rule group to your Firewall Manager policy, each account in your organization must first subscribe to that rule group\. After all accounts have subscribed, you can then add the rule group to a policy\. For more information, see [AWS Marketplace rule groups](classic-waf-managed-rule-groups.md)\.


## Getting started with AWS Firewall Manager to enable AWS WAF Classic rules

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.


## Tutorial: Creating a AWS Firewall Managerpolicy with hierarchical rules

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.
- **Note**  
In the latest version of AWS WAF, this capability is built in and doesn't require any special handling\. If you aren't already using AWS WAF Classic, use the latest version instead\. See [Creating an AWS Firewall Manager policy for AWS WAF](create-policy.md#creating-firewall-manager-policy-for-waf)\.


## Logging Web ACL traffic information

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.


## Listing IP addresses blocked by rate-based rules

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.


## How AWS WAF Classic works with Amazon CloudFront features

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.
- **Note**  
CloudFront can't distinguish between an HTTP status code 403 that is returned by your origin and one that is returned by AWS WAF Classic when a request is blocked\. This means that you can't return different custom error pages based on the different causes of an HTTP status code 403\.


## Security

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.


## AWS WAF Classic quotas

- **Note**  
This is **AWS WAF Classic** documentation\. You should only use this version if you created AWS WAF resources, like rules and web ACLs, in AWS WAF prior to November 2019, and you have not migrated them over to the latest version yet\. To migrate your resources, see [Migrating your AWS WAF Classic resources to AWS WAF](waf-migrating-from-classic.md)\.  
**For the latest version of AWS WAF**, see [AWS WAF](waf-chapter.md)\.

