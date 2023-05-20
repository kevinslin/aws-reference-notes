---
id: Conformance Packs
title: Conformance Packs
created: 1683841041000
updated: 1683841041000
---
# Conformance Packs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-config-developer-guide.git)
{% endhint %}

## Prerequisites

- **Note**  
When deploying cross\-account conformance packs, the name of the delivery Amazon S3 bucket should start with `awsconfigconforms`\.
- **Note**  
When deploying conformance packs to an organization, the name of the delivery Amazon S3 bucket should start with `awsconfigconforms`\.


## Process Checks

- **Note**  
However, you can update the compliance of the process check by choosing **Edit Compliance** and selecting the appropriate value from Compliant, Non\-Compliant or Not\-Applicable\.


## Conformance Pack Sample Templates

- **Important**  
 Conformance packs provide a general\-purpose compliance framework to help you create security, operational or cost\-optimization governance checks using managed or custom AWS Config rules and AWS Config remediation actions\. AWS conformance pack sample templates intend to help you create your own conformance packs with different or additional rules, input parameters and remediation actions that suit your environment\. The sample templates, including those related to compliance standards and industry benchmarks, are not designed to ensure your compliance with a specific governance standard\. They can neither replace your internal efforts nor guarantee that you will pass a compliance assessment\.


## Custom Conformance Pack

- **Note**  
**AWS Config Managed Rules** are predefined rules owned by AWS Config\.  
**AWS Config Custom Rules** are rules that you create from scratch\. There are two ways to create AWS Config custom rules: with Lambda functions \([AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-concepts.html#gettingstarted-concepts-function)\) and with Guard \([Guard GitHub Repository](https://github.com/aws-cloudformation/cloudformation-guard)\), a policy\-as\-code language\. AWS Config custom rules created with AWS Lambda are called *AWS Config Custom Lambda Rules* and AWS Config custom rules created with Guard are called *AWS Config Custom Policy Rules*\.
- **Note**  
Your file will contain a **Parameters** and **Resources** section\.
- **Note**  
When selecting the AWS Config Rules to build your custom conformance pack, check you have the resources provisioned within your account that will be evaluated for the AWS Config Rules\.
- **Note**  
When selecting the AWS Config rules to build your custom conformance pack, check that you have the resources that will be evaluated for the AWS Config rules provisioned within your account\. For more information, see [Supported Resource Types](https://docs.aws.amazon.com/config/latest/developerguide/resource-config-reference.html)\.


## Deploying a Conformance Pack (AWS CLI)

- **Note**  
For more information on creating a YAML template for a conformance pack, see [Custom Conformance Pack](https://docs.aws.amazon.com/config/latest/developerguide/custom-conformance-pack.html)\.


## Managing Conformance Packs Across all Accounts in Your Organization

- **Note**  
**For deployments across different regions**  
The API call to deploy rules and conformance packs across accounts is region specific\. At the organization level, you need to change the context of your API call to a different region if you want to deploy rules in other regions\. For example, to deploy a rule in US East \(N\. Virginia\), change the region to US East \(N\. Virginia\) and then call `PutOrganizationConfigRule`\.  
**For accounts within an organzation**  
If a new account joins an organization, the rule or conformance pack is deployed to that account\. When an account leaves an organization, the rule or conformance pack is removed\.  
If you deploy an organizational rule or conformance pack in an organization administrator account, and then establish a delegated administrator and deploy an organizational rule or conformance pack in the delegated administrator account, you won't be able to see the organizational rule or conformance pack in the organization administrator account from the delegated administrator account or see the organizational rule or conformance pack in the delegated administrator account from organization administrator account\. The [DescribeOrganizationConfigRules](https://docs.aws.amazon.com/config/latest/APIReference/API_DescribeOrganizationConfigRules.html) and [DescribeOrganizationConformancePacks](https://docs.aws.amazon.com/config/latest/APIReference/API_DescribeOrganizationConformancePacks.html) APIs can only see and interact with the organization\-related resource that were deployed from within the account calling those APIs\.   
**Retry mechanism for new accounts added to an organization**  
Deployment of existing organizational rules and conformance packs will only be retried for 7 hours after an account is added to your organization if a recorder is not available\. You are expected to create a recorder if one doesn't exist within 7 hours of adding an account to your organization\.

