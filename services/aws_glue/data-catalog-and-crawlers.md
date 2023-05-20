---
id: Data Catalog and crawlers
title: Data Catalog and crawlers
created: 1683841041000
updated: 1683841041000
---
# Data Catalog and crawlers

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-glue-developer-guide.git)
{% endhint %}

## AWS Glue databases

- **Note**  
When you delete a database from the AWS Glue Data Catalog, all the tables in the database are also deleted\.


## Adding classifiers to a crawler

- **Note**  
If your data format is recognized by one of the built\-in classifiers, you don't need to create a custom classifier\.
- **Note**  
If the built\-in CSV classifier does not create your AWS Glue table as you want, you might be able to use one of the following alternatives:  
Change the column names in the Data Catalog, set the `SchemaChangePolicy` to LOG, and set the partition output configuration to `InheritFromTable` for future crawler runs\.
Create a custom grok classifier to parse the data and assign the columns that you want\.
The built\-in CSV classifier creates tables referencing the `LazySimpleSerDe` as the serialization library, which is a good choice for type inference\. However, if the CSV data contains quoted strings, edit the table definition and change the SerDe library to `OpenCSVSerDe`\. Adjust any inferred types to STRING, set the `SchemaChangePolicy` to LOG, and set the partitions output configuration to `InheritFromTable` for future crawler runs\. For more information about SerDe libraries, see [SerDe Reference](https://docs.aws.amazon.com/athena/latest/ug/serde-reference.html) in the Amazon Athena User Guide\.

