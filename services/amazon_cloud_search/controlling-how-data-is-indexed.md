---
id: Controlling How Data is Indexed
title: Controlling How Data is Indexed
created: 1683841041000
updated: 1683841041000
---
# Controlling How Data is Indexed

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cloudsearch-developer-guide.git)
{% endhint %}

## Preparing Your Data

- **Important**  
Before uploading data to an Amazon CloudSearch domain, follow these guidelines:  
Group documents into *batches* before you upload them\. Continuously uploading batches that consist of only one document has a huge, negative impact on the speed at which Amazon CloudSearch can process your updates\. Instead, create batches that are as close to the limit as possible and upload them less frequently\. For more information on maximum batch size and upload frequency, see [Understanding Amazon CloudSearch Limits](limits.md)\.
A domain's document and search endpoints remain the same for the life of the domain\. You should cache the endpoints rather than retrieving them before every upload or search request\. Querying the Amazon CloudSearch configuration service by calling `aws cloudsearch describe-domains` or `DescribeDomains` before every request will likely result in your requests being throttled\.
- **Note**  
To delete documents, you upload document batches that contain delete operations\. You are billed for the total number of document batches uploaded to your search domain, including batches that contain delete operations\. For more information about Amazon CloudSearch pricing, see [aws\.amazon\.com/cloudsearch/pricing/](http://aws.amazon.com/cloudsearch/pricing/)\.
- **Note**  
Currently, only CSV files are parsed to automatically extract custom field data and generate multiple documents\.


## Configuring Index Fields

- **Important**  
If you change the type of a field and have documents in your index that contain data that is incompatible with the new field type, all fields being processed are put in the `FailedToValidate` state when you run indexing and the indexing operation fails\. Rolling back the incompatible configuration change will enable you to successfully rebuild your index\. If the change is necessary, you must update or remove the incompatible documents from your index to use the new configuration\.
- **Note**  
When you add fields or modify existing fields, you must explicitly issue a request to re\-index your data when you are done making configuration changes\. For more information, see [Indexing Document Data](indexing.md)\.
- **Note**  
When you add fields or modify existing fields, you must explicitly issue a request to re\-index your data when you are done making configuration changes\. For more information, see [Indexing Document Data](indexing.md)\.


## Using Dynamic Fields

- **Note**  
The options you can configure for dynamic fields are the same as for [static fields](configuring-index-fields.md)\. Similarly, document field names that match a dynamic field must meet all the same criteria as static field names\.
- **Note**  
When you create a dynamic field with the name `*`, it means that your index can potentially contain any valid field name\. This also means that you can reference any valid field name in your search requests, whether or not it actually exists in your index\.


## Configuring Analysis Schemes

- **Important**  
To use an analysis scheme, you must apply it to one or more `text` or `text-array` fields and rebuild the index\. You can configure a field's analysis scheme from the **Indexing options** tab\. To rebuild your index, choose **Actions**, **Run indexing**\.
- **Important**  
To use an analysis scheme, you must apply it to one or more `text` or `text-array` fields and rebuild the index\. You can configure a field's analysis scheme with the `aws cloudsearch define-index-field` command\. To rebuild the index, call `aws cloudsearch index-documents`\.
- **Important**  
To use an analysis scheme, you must apply it to one or more `text` or `text-array` fields and rebuild the index\. You can configure a field's analysis scheme with the define index field method\. To rebuild your index, you use the index documents method\.

