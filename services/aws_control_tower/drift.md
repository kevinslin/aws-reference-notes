---
id: Drift
title: Drift
created: 1683841041000
updated: 1683841041000
---
# Drift

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## Types of Governance Drift

- **Note**  
In Service Catalog, the Account Factory provisioned product that represents the account is not updated to remove the account\. Instead, the provisioned product is displayed as `TAINTED` and in an error state\. To clean up, go to the Service Catalog, choose the provisioned product, and then choose **Terminate**\.


## If you manage resources outside of AWS Control Tower

- **Note**  
AWS Service Catalog handles changes differently than AWS Control Tower\. AWS Service Catalog may create a change in governance posture when it reconciles your changes\. For more information about updating a provisioned product, see [Updating Provisioned Products](https://docs.aws.amazon.com/servicecatalog/latest/userguide/enduser-update.html) in the AWS Service Catalog documentation\.
- **Note**  
The action of deleting your Security OU is not to be performed without due consideration\. The action could create compliance concerns if logging is suspended temporarily, and because some controls might not be enforced\.
- **Note**  
In AWS Service Catalog, the Account Factory displays the parameters that were specified in the console when you created a provisioned product\. However, the original account email address is not updated automatically when the account email address changes\. That’s because the account is conceptually contained within the provisioned product; it is not the same as the provisioned product\. To update this value, you must update the provisioned product, which may cause a change in governance posture\.
- **Note**  
In AWS Service Catalog, the Account Factory is updated to remove the deleted OU from the list of available OUs into which you can provision an account\.
- **Note**  
In AWS Service Catalog, the Account Factory provisioned product that represents the governed account is not updated to delete the account\. Instead, the provisioned product is displayed as `TAINTED` and in an error state\. To clean up, go to AWS Service Catalog, choose the provisioned product, and then choose **Terminate**\.

