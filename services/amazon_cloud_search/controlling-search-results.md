---
id: Controlling Search Results
title: Controlling Search Results
created: 1683841041000
updated: 1683841041000
---
# Controlling Search Results

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cloudsearch-developer-guide.git)
{% endhint %}

## Sorting Results

- **Tip**  
To sort results randomly, you can use a simple `_rand` expression:


## Paginating Results

- **Important**  
When you use a cursor to page through a result set that is sorted by document score \(`_score`\), you can get inconsistent results if the index is updated between requests\. This can also occur if your domain's replication count is greater than one, because updates are applied in an eventually consistent manner across the instances in the domain\. If this is an issue, avoid sorting the results by score\. You can either use the `sort` option to sort by a particular field, or use `fq` instead of `q` to specify your search criteria\. \(Document scores are not calculated for filter queries\.\)

