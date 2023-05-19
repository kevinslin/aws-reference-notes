---
id: Amazon CloudSearch API Reference
title: Amazon CloudSearch API Reference
created: 1683841041000
updated: 1683841041000
---
# Amazon CloudSearch API Reference

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cloudsearch-developer-guide.git)
{% endhint %}

## Search API Reference

- **Important**  
You must URL\-encode special characters in the query string\. For example, you must encode the `=` operator in a structured query as `%3D`: `(term+field%3Dtitle+'star'`\)\. Amazon CloudSearch returns an `InvalidQueryString` error if special characters are not URL\-encoded\. For a complete reference of URL\-encodings, see the W3C [HTML URL Encoding Reference](http://www.w3schools.com/tags/ref_urlencode.asp)\.
- **Important**  
A domain's document and search endpoints remain the same for the life of the domain\. You should cache the endpoints rather than retrieving them before every upload or search request\. Querying the Amazon CloudSearch configuration service by calling `aws cloudsearch describe-domains` or `DescribeDomains` before every request is likely to result in your requests being throttled\.

