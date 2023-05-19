---
id: Filtering results
title: Filtering results
created: 1683841041000
updated: 1683841041000
---
# Filtering results

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-personalize-developer-guide.git)
{% endhint %}

## Filter expressions

- **Note**  
Amazon Personalize ignores case only when matching event types\.


## Filtering real-time recommendations

- **Note**  
To filter recommendations using a filter with parameters and a campaign deployed before November 10, 2020, you must redeploy the campaign by using the [UpdateCampaign](API_UpdateCampaign.md) operation or create a new campaign\.
- **Important**  
For filter expressions that use an `INCLUDE` element to include items, you must provide values for all parameters that are defined in the expression\. For filters with expressions that use an `EXCLUDE` element to exclude items, you can omit the `filter-values`\. In this case, Amazon Personalize doesn't use that portion of the expression to filter recommendations\.
- **Important**  
You can't delete a filter while a batch inference job is in progress\.
- **Important**  
To filter recommendations using a filter with parameters and a campaign you deployed before November 10, 2020, you must re\-deploy the campaign by using the [UpdateCampaign](API_UpdateCampaign.md) call or create a new campaign\.
- **Important**  
For filter expressions that use an `INCLUDE` element to include items, you must provide values for all parameters that are defined in the expression\. For filters with expressions that use an `EXCLUDE` element to exclude items, you can omit the `filter-values`\. In this case, Amazon Personalize doesn't use that portion of the expression to filter recommendations\.
- **Important**  
To filter recommendations using a filter with parameters and a campaign you deployed before November 10, 2020, you must re\-deploy the campaign by using the [UpdateCampaign](API_UpdateCampaign.md) call or create a new campaign\.
- **Important**  
For filter expressions that use an `INCLUDE` element to include items, you must provide values for all parameters that are defined in the expression\. For filters with expressions that use an `EXCLUDE` element to exclude items, you can omit the `filter-values`\. In this case, Amazon Personalize doesn't use that portion of the expression to filter recommendations\.

