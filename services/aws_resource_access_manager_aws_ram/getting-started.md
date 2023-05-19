---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-resource-access-manager-user-guide.git)
{% endhint %}

## Terms and concepts

- **Note**  
This policy uses `"Principal": "*"` and then uses the `"Condition"` element to restrict permissions to identities that match the specified `PrincipalOrgID`\. For more information, see [Implications of using "Principal": "\*" in a resource\-based policy](#term-principal-star)\.


## Sharing your resources

- **Important**  
You must enable sharing with AWS Organizations by using the AWS RAM console or the [enable\-sharing\-with\-aws\-organization](https://docs.aws.amazon.com/cli/latest/reference/ram/enable-sharing-with-aws-organization.html) AWS CLI command\. This ensures that the `AWSServiceRoleForResourceAccessManager` service\-linked role is created\. If you enable trusted access with AWS Organizations by using the AWS Organizations console or the [ enable\-aws\-service\-access](https://docs.aws.amazon.com/cli/latest/reference/organizations/enable-aws-service-access.html) AWS CLI command, the `AWSServiceRoleForResourceAccessManager` service\-linked role isn't created, and you can't share resources within your organization\.
- **Considerations**
- **Note**  
To obtain the unique ARN for an IAM user, [view the list of users in the IAM console](https://console.aws.amazon.com/iamv2/home?#/users), use the [https://docs.aws.amazon.com/cli/latest/reference/iam/get-user.html](https://docs.aws.amazon.com/cli/latest/reference/iam/get-user.html) AWS CLI command, or the [https://docs.aws.amazon.com/IAM/latest/APIReference/API_GetUser.html](https://docs.aws.amazon.com/IAM/latest/APIReference/API_GetUser.html) API action\.
- **Note**  
If you want to use a customer managed permission with a resource type in this resource share, you can either use an existing customer managed permission or create a new customer managed permission\. Make note of the ARN for the customer managed permission, and then create the resource share\. For more information, see [Create a customer managed permission](create-customer-managed-permissions.md#create_cmp)\.

