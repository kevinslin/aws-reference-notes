---
id: Querying For More Information
title: Querying For More Information
created: 1683841041000
updated: 1683841041000
---
# Querying For More Information

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cloudsearch-developer-guide.git)
{% endhint %}

## Getting Suggestions

- **Tip**  
Instead of configuring suggesters to use *all* possibilities from *all* documents, consider indexing the most popular 1,000 or 10,000 search queries and configuring suggesters to use those\. You can store the queries in a separate Amazon CloudSearch index or in a field used only for suggestions\.
- **Important**  
After you add a suggester to your search domain, you must run indexing before you can use it to retrieve suggestions\. As you add and delete documents, you must periodically rebuild your index to update the suggestions\. Suggestions won't reflect added or deleted documents until you call `IndexDocuments`\.

