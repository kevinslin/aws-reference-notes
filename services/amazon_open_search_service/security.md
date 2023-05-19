---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## Identity and Access Management

- **Important**  
VPC support introduces some additional considerations to OpenSearch Service access control\. For more information, see [About access policies on VPC domains](vpc.md#vpc-security)\.
- **Note**  
Users with the AWS managed `AmazonOpenSearchServiceReadOnlyAccess` policy can't see cluster health status on the console\. To allow them to see cluster health status \(and other OpenSearch data\), add the `es:ESHttpGet` action to an access policy and attach it to their accounts or roles\.
- **Note**  
After you add one or more OpenSearch APIs to any tag\-based policy, you must perform a single [tag operation](managedomains-awsresourcetagging.md) \(such as adding, removing, or modifying a tag\) in order for the changes to take effect on a domain\. You must be on service software R20211203 or later to include OpenSearch API operations in tag\-based policies\.
- **Note**  
If you enabled VPC access for your domain, you can't configure an IP\-based policy\. Instead, you can use [security groups](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) to control which IP addresses can access the domain\. For more information, see [About access policies on VPC domains](vpc.md#vpc-security)\.
- **Note**  
The service ignores parameters passed in URLs for HTTP POST requests that are signed with Signature Version 4\.


## Fine-grained access control

- **Note**  
If a resource\-based access policy contains IAM roles or users, clients must send signed requests using AWS Signature Version 4\. As such, access policies can conflict with fine\-grained access control, especially if you use the internal user database and HTTP basic authentication\. You can't sign a request with a username and password *and* IAM credentials\. In general, if you enable fine\-grained access control, we recommend using a domain access policy that doesn't require signed requests\.
- **Note**  
The permissions that you choose to grant to your users vary widely based on use case\. We cannot feasibly cover all scenarios in this documentation\. As you're determining which permissions to grant your users, make sure to reference the OpenSearch cluster and index permissions mentioned in the following sections, and always follow the [principle of least privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege)\.
- **Tip**  
If you apply the standard masking to a field, OpenSearch Service uses a secure, random hash that can cause inaccurate aggregation results\. To perform aggregations on masked fields, use pattern\-based masking instead\.
- **Note**  
OpenSearch Dashboards maintains a separate index for each tenant, and creates an index template called `tenant_template`\. Do not delete or modify the `tenant_template` index, as it could cause OpenSearch Dashboards to malfunction if the tenant index mapping is misconfigured\.
- **Tip**  
If you use the internal user database, you can use [curl](https://curl.haxx.se/) to make requests and test your domain\. Try the following sample commands:


## Amazon Cognito authentication for OpenSearch Dashboards

- **Tip**  
The first time you configure a domain to use Amazon Cognito authentication for OpenSearch Dashboards, we recommend using the console\. Amazon Cognito resources are extremely customizable, and the console can help you identify and understand the features that matter to you\.
- **Note**  
The user pool and identity pool must be in the same AWS Region\. You can use the same user pool, identity pool, and IAM role to add Amazon Cognito authentication for Dashboards to multiple OpenSearch Service domains\. To learn more, see [Quotas](#cognito-auth-limits)\.
- **Note**  
Amazon Cognito is not available in all AWS Regions\. For a list of supported Regions, see [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/cognito_identity.html)\. You don't need to use the same Region for Amazon Cognito that you use for OpenSearch Service\.
- **Note**  
If you configured [fine\-grained access control](fgac.md) and use an open or IP\-based access policy, you can skip this step\.
- **Important**  
Just like the default role, Amazon Cognito must be part of each additional role's trust relationship\. For details, see [Creating Roles for Role Mapping](https://docs.aws.amazon.com/cognito/latest/developerguide/role-based-access-control.html#creating-roles-for-role-mapping) in the *Amazon Cognito Developer Guide*\.
- **Important**  
If you no longer need the Amazon Cognito user pool and identity pool, delete them\. Otherwise, you continue to incur charges\.

