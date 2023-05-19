---
id: Searching indexes
title: Searching indexes
created: 1683841041000
updated: 1683841041000
---
# Searching indexes

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-kendra-developer-guide.git)
{% endhint %}

## Querying an index

- **Note**  
You can use this code to filter document attributes\. The topic [Filtering queries](filtering.md) contains examples that you can use to replace the following code\.


## Query suggestions

- **Note**  
The time for your updated settings to take effect depends on the updates you make and the number of search queries in your index\.
- **Note**  
Amazon Kendra learns new suggestions based on new queries added to the query log from the time you last cleared suggestions\.


## Filtering on user context

- **Note**  
User context filtering isn't an authentication or authorization control for your content\. It doesn't do user authentication on the user and groups sent to the `Query` API\. It is up to your application to ensure that the user and group information sent to `Query` API is authenticated and authorized\.

