---
id: Providing data products
title: Providing data products
created: 1683841041000
updated: 1683841041000
---
# Providing data products

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-data-exchange-user-guide.git)
{% endhint %}

## Publishing guidelines

- **Note**  
If you're enrolled in the Extended Provider Program \(currently in Preview\), sections 2 and 3 below don't apply and are replaced with the restrictions set forth in the Extended Provider Program Addendum to the Terms and Conditions for AWS Marketplace Providers\. For more information about eligibility for the Extended Provider Program, contact [ AWS Support](https://console.aws.amazon.com/support/home#/case/create?issueType=customer-service) or send an email message to [adx\-providers@amazon\.com](mailto://adx-providers@amazon.com)\.


## Product details

- **Note**  
You can't modify the visibility of a product after it has been created\.
- **Note**  
The third and fourth options are only available to eligible providers enrolled in the Extended Provider Program who have agreed to the Extended Provider Program Addendum to the Terms and Conditions for AWS Marketplace Providers\. The Extended Provider Program is currently in preview and subject to Section 2 of the [AWS Service Terms](https://aws.amazon.com/service-terms/) \(under *Betas and Previews*\)\. For information about eligibility, contact [AWS Support](https://console.aws.amazon.com/support/home#/case/create?issueType=customer-service) or send an email message to [dataexchangehelp@amazon\.com](mailto://dataexchangehelp@amazon.com)\.  
The fourth option is only available to eligible providers who have agreed to the AWS Business Associate Addendum, as well as the AWS Data Exchange Addendum to the AWS Business Associate Addendum\.
- **Note**  
You can use Markdown templates as a starting point for the long description of a number of popular product types\. For more information, see [Product description templates](product-description-templates.md)\.
- **Note**  
You can't choose both **No historical revisions** and **No future revisions**\. That would create a product with no revisions and no data\.
- **Note**  
A data dictionary is attached to a product and associated with a data set\. If you want to have more than one data dictionary for potential subscribers to evaluate, you can create two or more versions of the same product with the same data sets\. Then, add a different data dictionary to each product\.
- **Note**  
Samples are attached to a product and associated with a data set\. If you want to have more than 10 samples for potential subscribers to evaluate, you can create two or more versions of the same product with the same data sets\. Then, add up to 10 samples to each product\.


## Getting started

- **Important**  
You can't change the AWS account that you use to list a product on AWS Marketplace\. Only data sets owned by that account can be included in products published by that account\. Only AWS accounts that are registered to provide data products on AWS Marketplace and AWS Data Exchange can publish products\.


## Publishing a new product

- **Important**  
As of July 22, 2021, new and existing providers can automatically publish revisions to data sets\. All new products on AWS Data Exchange default to automatic revision publishing\. If you have created existing products on AWS Data Exchange before July 22, 2021, you need to migrate them to automatic revision publishing\.   
For more information, see [Migrating an existing product to automatic revision publishing](updating-products.md#migrate-product)\.
- **Note**  
If you're an existing provider and have not yet migrated all of your products to automatic revision publishing, you must publish your revision manually\. For more information, see [Publishing a new data set revision using manual revision publishing](updating-products.md#manual-publish-revision)\.
- **Note**  
You can copy a public, private, published, or unpublished product\. Custom oﬀers associated with the product will not be copied, but public oﬀers will be copied\.
- **Note**  
Metered costs apply to all API data sets in a product\. Therefore, if you want to charge different prices for the same dimension for different API data sets, we recommend that you create these data sets in different products\.
- **Note**  
If you have a resource policy that explicitly denies AWS Data Exchange from doing this invocation, you must remove or limit this deny\.
- **Note**  
You can copy a public, private, published, or unpublished product\. Custom oﬀers associated with the product will not be copied, but public oﬀers will be copied\.
- **Note**  
You can copy a public, private, published, or unpublished product\. Custom oﬀers associated with the product will not be copied, but public oﬀers will be copied\.


## Updating products

- **Important**  
A provider can revoke subscriber access to a revision and then delete the assets of the revision using the console or the AWS Data Exchange API\. For more information, see [Revoking revisions](#revoking-revisions)\.
- **Important**  
As of July 22, 2021, new and existing providers can automatically publish revisions to data sets\. All new products on AWS Data Exchange default to automatic revision publishing\. If you have created existing products on AWS Data Exchange before July 22, 2021, you need to migrate them to automatic revision publishing\.  
For more information, see [Migrating an existing product to automatic revision publishing](#migrate-product)\.
- **Important**  
As of July 22, 2021, new and existing providers can automatically publish revisions to data sets\. All new products on AWS Data Exchange default to automatic revision publishing\. If you have created existing products on AWS Data Exchange before July 22, 2021, you need to migrate them to automatic revision publishing\.  
If you have existing products, you can migrate your existing products from manual revision publishing to automatic revision publishing\. Automatic revision publishing simplifies the data set revision publishing process by making your revision immediately available to subscribers when you finalize it\.
- **Important**  
The AWS Identity and Access Management \(IAM\) permission `dataexchange:StartChangeSet` is required for self\-service and bulk migration\.


## Creating offers

- **Note**  
If you set up a flexible payment schedule for a custom private offer, the offer can't be set to auto\-renewal\.


## Subscription verification

- **Note**  
Subscription verification is automatically enabled for all public products from Extended Provider Program providers that contain non\-public, personal information\.
- **Important**  
The subscriber must enter information in each field, but AWS Data Exchange doesn't review or validate the information\. You're solely responsible for reviewing and verifying the information that the subscriber provides\.
- **Note**  
Each subscription request is uniquely identified using its ID\. The ID is visible to both the provider and the subscriber\. You can use the subscription request ID in your communications with the subscriber\.
- **Note**  
You will not receive email notifications for subscription request status changes that you have initiated yourself \(for example, when you approve a subscription\)\.
- **Important**  
The subscriber information you collect through subscription verification must be used in accordance with AWS Marketplace Terms and Conditions\.

