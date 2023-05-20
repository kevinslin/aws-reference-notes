---
id: Subscribing to data products
title: Subscribing to data products
created: 1683841041000
updated: 1683841041000
---
# Subscribing to data products

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-data-exchange-user-guide.git)
{% endhint %}

## Product subscriptions

- **Important**  
The data subscription agreement \(DSA\) sets forth the provider’s terms and conditions for the data product\. The use of any data product subscribed to on AWS Data Exchange must also be in compliance with the AWS Customer Agreement or other agreement governing your use of AWS services\.
- **Note**  
Data products that are part of the [Open Data on AWS](https://aws.amazon.com/opendata/) program are free for anyone to use and do not require a subscription\. For more information, see [Using Open Data on AWS data sets](open-data.md)\.
- **Important**  
If the data provider has indicated that the product contains any categories of sensitive or personal data, for example, mobile IDs, it will be displayed with the product details\. For more information about the categories of sensitive data, see [Sensitive categories of information](product-details.md#sensitive-information)\.  
If the data provider has indicated that the product contains protected health information \(PHI\) subject to the Health Insurance Portability and Accountability Act of 1996 \(HIPAA\), you may not export the product's data sets into your AWS account unless such AWS account is designated as a HIPAA account \(as defined in the AWS Business Associate Addendum found in [AWS Artifact](https://docs.aws.amazon.com/artifact/latest/ug/what-is-aws-artifact.html)\)\.
- **Note**  
For information about data sets and revisions, including details about what you have access to in your subscription, see [Data sets and revisions](#product-sub-revisions)\.
- **Important**  
If you enable auto\-renew, and the product's offer terms have changed at the time of renewal, then the new product offer terms \(including new price and new DSA\) apply\. This ensures that you keep access to the data regardless of potential changes to offer terms\.


## Subscribing to a product

- **Note**  
By subscribing to a product, you agree that your use of the product is subject to the provider's offer terms including pricing information and Data Subscription Agreement\.  
You also agree and acknowledge that AWS may share information about the transaction \(including your payment terms and product usage metrics\) with the respective seller, reseller, or underlying provider, as applicable, in accordance with the [AWS Privacy Notice](https://aws.amazon.com/privacy/)\. AWS will issue invoices and collect payments from you on behalf of the provider through your AWS account\. Your use of AWS services remains subject to the AWS Customer Agreement or other agreement with AWS governing your use of such services\.
- **Important**  
We recommend that you consider Amazon S3 security features when exporting data to Amazon S3\. See [Security best practices for Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/security-best-practices.html) for general guidelines and best practices\.
- **Note**  
You lose access to a product's datashares after your subscription expires\.


## Subscription verification for subscribers

- **Note**  
You can cancel a pending subscription request at any time as long as it hasn't expired or already been processed\.
- **Note**  
You will not receive email notifications for subscription request status changes that you have initiated yourself \(for example, cancelling a subscription\)\.


## Sharing license subscriptions in an organization

- **Note**  
For more information about AWS Organizations, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)\.


## Bring Your Own Subscription (BYOS) offers

- **Important**  
With BYOS offers, you're migrating a subscription that predates the availability of this product on AWS\. AWS might verify your BYOS offer with the existing subscription agreement\. If AWS cannot verify your BYOS offer, the offer and entitlements can be revoked without notice\.


## Private products and offers

- **Note**  
Unlike Bring Your Own Subscription \(BYOS\) offers, private offers are not required to be based on an existing subscription that predates the product's availability on AWS Data Exchange\.


## Managing subscriptions

- **Note**  
If you require immediate removal of a subscription, contact AWS Data Exchange Customer Support by using the [AWS Support Center](https://console.aws.amazon.com/support/home#/case/create?issueType=customer-service&serviceCode=service-data-exchange )\.


## Tutorial: Subscribe to AWS Data Exchange Heartbeat

- **Note**  
It can take a few minutes for your subscription to become active after you choose **Subscribe**\. If you choose **Export** before the subscription is active, you are prompted to wait until it is complete\. After your subscription is active, your export will begin\.  
Navigating away from this page prior to your subscription becoming active will not prevent the subscription from processing\. It will prevent your data export from occurring\.


## Tutorial: Subscribe to Worldwide Event Attendance

- **Note**  
A subscription to this product might require Amazon Redshift cluster infrastructure, which could incur extra costs\. To query the Amazon Redshift data, an Amazon Redshift cluster running on an RA3 instance is required\.

