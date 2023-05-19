---
id: Large Data Migration
title: Large Data Migration
created: 1683841041000
updated: 1683841041000
---
# Large Data Migration

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-snowball-developer-guide.git)
{% endhint %}

## Planning Your Large Transfer

- **Note**  
For large data transfers, we recommend using the Amazon S3 adapter to transfer your data\.
- **Note**  
Metadata operations are performed for each file that's transferred\. Regardless of a file's size, this overhead remains the same\. Therefore, you get faster performance by compressing small files into a larger bundle, batching your files, or transferring larger individual files\.

