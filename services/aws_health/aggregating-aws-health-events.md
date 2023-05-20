---
id: Aggregating AWS Health events
title: Aggregating AWS Health events
created: 1683841041000
updated: 1683841041000
---
# Aggregating AWS Health events

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-personal-health-dashboard.git)
{% endhint %}

## Organizational view (console)

- **Note**  
If you want to allow users access to this feature in the management account, they must have permissions such as the [https://console.aws.amazon.com/iam/home?#/policies/arn:aws:iam::aws:policy/AWSHealthFullAccess](https://console.aws.amazon.com/iam/home?#/policies/arn:aws:iam::aws:policy/AWSHealthFullAccess) policy\. For more information, see [AWS Health identity\-based policy examples](security_iam_id-based-policy-examples.md)\.
- **Important**  
 For customers in the AWS GovCloud \(US\) Regions:   
 Before closing your account, back up and then delete your policy data and other account resources\. You will no longer have access to them after you close the account\.
- **Note**  
When you enable this feature, the AWS Health console can display public events from the [Service Health Dashboard](https://status.aws.amazon.com) for the last 7 days\. These public events aren't specific to accounts in your organization\. Events from the Service Health Dashboard provide public information about the regional availability of AWS services\.


## Organizational view (CLI)

- **Note**  
If you want to allow users access to the management account for the organizational view feature, they must have permissions such as the [https://console.aws.amazon.com/iam/home?#/policies/arn:aws:iam::aws:policy/AWSHealthFullAccess](https://console.aws.amazon.com/iam/home?#/policies/arn:aws:iam::aws:policy/AWSHealthFullAccess) policy\. For more information, see [AWS Health identity\-based policy examples](security_iam_id-based-policy-examples.md)\.
- **Note**  
You must have a [Business](http://aws.amazon.com/premiumsupport/plans/business/) or [Enterprise](http://aws.amazon.com/premiumsupport/plans/enterprise/) support plan to call the AWS Health API\.
You must use the US East \(N\. Virginia\) Region endpoint\.
- **Note**  
Enabling this feature is an asynchronous process and takes time to complete\. You can call the [DescribeHealthServiceStatusForOrganization](https://docs.aws.amazon.com/health/latest/APIReference/API_DescribeHealthServiceStatusForOrganization.html) operation to check the status of the process\.
- **Note**  
AWS Health doesn't record events that occurred in your organization before you enabled organizational view\.
- **Important**  
 For customers in the AWS GovCloud \(US\) Regions:   
 Before closing your account, back up and then delete your policy data and other account resources\. You will no longer have access to them after you close the account\.
- **Note**  
You can also disable the organizational feature by using the Organizations [DisableAWSServiceAccess](https://docs.aws.amazon.com/organizations/latest/APIReference/API_DisableAWSServiceAccess.html) API operation\. After you call this operation, AWS Health stops aggregating events for all other accounts in your organization\. If you call the AWS Health API operations for organizational view, AWS Health returns an error\. AWS Health continues to aggregate health events for your AWS account\.

