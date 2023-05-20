---
id: CA administration
title: CA administration
created: 1683841041000
updated: 1683841041000
---
# CA administration

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-private-ca-user-guide.git)
{% endhint %}

## Creating a private CA

- **Note**  
Your account is charged a monthly price for each private CA starting from the time that you create it\.  
For the latest AWS Private CA pricing information, see [AWS Private Certificate Authority Pricing](https://aws.amazon.com/private-ca/pricing/)\. You can also use the [AWS pricing calculator](https://calculator.aws/#/createCalculator/certificateManager) to estimate costs\.


## Installing CA certificate

- **Note**  
Procedures for creating or obtaining an external trust services provider are outside the scope of this guide\.


## Listing private CAs

- **Note**  
You can customize the columns that you want to display, as well as other settings, by choosing the gear icon in the upper\-right corner of the console\.


## Adding tags

- **Note**  
To attach tags to a private CA during the creation procedure, a CA administrator must first associate an inline IAM policy with the `CreateCertificateAuthority` action and explicitly allow tagging\. For more information, see [Attaching tags to a CA at the time of creation](auth-InlinePolicies.md#policy-tag-ca)\.


## Updating a CA

- **Note**  
For all status values except `DELETED` and `FAILED`, you are billed for the CA\.


## Deleting a CA

- **Important**  
A private CA can be deleted if it is in the `PENDING_CERTIFICATE`, `CREATING`, `EXPIRED`, `DISABLED`, or `FAILED` state\. In order to delete a CA in the `ACTIVE` state, you must first disable it, or else the delete request results in an exception\. If you are deleting a private CA in the `PENDING_CERTIFICATE` or `DISABLED` state, you can set the length of its restoration period from 7\-30 days, with 30 being the default\. During this period, status is set to `DELETED` and the CA is restorable\. A private CA that is deleted while in the `CREATING` or `FAILED` state has no assigned restoration period and cannot be restored\. For more information, see [Restoring a private CA](PCARestoreCA.md)\.  
You are not charged for a private CA after it has been deleted\. However, if a deleted CA is restored, you are charged for the time between deletion and restoration\. For more information, see [Pricing](PcaPricing.md)\.


## Restoring a CA

- **Note**  
You are not charged for a private CA after it has been deleted\. However, if a deleted CA is restored, you are charged for the time between deletion and restoration\. For more information, see [Pricing](PcaPricing.md)\.

