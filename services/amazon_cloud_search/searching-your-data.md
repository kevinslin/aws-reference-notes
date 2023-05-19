---
id: Searching Your Data
title: Searching Your Data
created: 1683841041000
updated: 1683841041000
---
# Searching Your Data

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cloudsearch-developer-guide.git)
{% endhint %}

## Submitting Search Requests

- **Important**  
Search endpoints don't change: A domain's document and search endpoints remain the same for the life of the domain\. You should cache the endpoints rather than retrieving them before every upload or search request\. Querying the Amazon CloudSearch configuration service by calling `aws cloudsearch describe-domains` or `DescribeDomains` before every request is likely to result in your requests being throttled\.
IP addresses **do** change: Your domain's IP address *can* change over time, so it's important to cache the endpoint as shown in the console and returned by the `aws cloudsearch describe-domains` command rather than the IP address\. You should also re\-resolve the endpoint DNS to an IP address regularly\. For more information, see [Setting the JVM TTL for DNS Name Lookups](https://docs.aws.amazon.com/sdk-for-java/latest/developer-guide/java-dg-jvm-ttl.html)\.
- **Note**  
The AWS SDKs return fields as arrays\. Single\-value fields are returned as arrays with one element, such as:
- **Important**  
Special characters in the query string must be URL\-encoded\. For example, you must encode the `=` operator in a structured query as `%3D`: `(term+field%3Dtitle+'star')`\. If you don't encode the special characters when you submit the search request, you'll get an `InvalidQueryString` error\.


## Constructing Compound Queries

- **Important**  
You must URL\-encode special characters in the query string\. For example, you must encode the `=` operator in a structured query as `%3D`: `(term+field%3Dtitle+'star'`\)\. Amazon CloudSearch returns an `InvalidQueryString` error if special characters are not URL\-encoded\. For a complete reference of URL\-encodings, see the W3C [HTML URL Encoding Reference](http://www.w3schools.com/tags/ref_urlencode.asp)\.


## Searching for Text in Amazon CloudSearch

- **Note**  
When performing wildcard searches on text fields, keep in mind that Amazon CloudSearch tokenizes the text fields during indexing and performs stemming according to the analysis scheme configured for the field\. Normally, Amazon CloudSearch performs the same text processing on the search query\. However, when you search for a prefix with the wildcard operator \(\*\) or `prefix` operator, no stemming is performed on the prefix\. This means that a search for a prefix that ends in `s` won't match the singular version of the term\. This can happen for any term that ends in `s`, not just plurals\. For example, if you search the `actor` field in the sample movie data for `Anders`, there are three matching movies\. If you search for `Ander*`, you get those movies as well as several others\. However, if you search for `Anders*` there are no matches\. This is because the term is stored in the index as `ander`, `anders` does not appear in the index\. For more information about how Amazon CloudSearch processes text and how it can affect searches, see [Text Processing in Amazon CloudSearch](text-processing.md)\.


## Searching and Ranking Results by Geographic Location

- **Tip**  
For these sample queries to work, you must [configure your index](configuring-index-fields.md) with a `latlon` field and have `location` data in your documents:


## Searching DynamoDB Data

- **Note**  
To upload data from DynamoDB, you must have permission to access both the service and the resources you want to upload\. For more information, see [Using IAM to Control Access to DynamoDB Resources](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/UsingIAMWithDDB.html)\.
- **Important**  
When you use a DynamoDB table to configure a domain, the data is not automatically uploaded to the domain for indexing\. You must upload the data for indexing as a separate step after you configure the domain\.

