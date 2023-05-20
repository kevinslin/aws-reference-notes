---
id: AWS Config Rules
title: AWS Config Rules
created: 1683841041000
updated: 1683841041000
---
# AWS Config Rules

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-config-developer-guide.git)
{% endhint %}

## Components of a Rule

- **Note**  
Before using pip, make sure it is installed on your machine\.
- **Note**  
Before using pip, make sure it is installed on your machine\.
- **Note**  
To use the RDKLib, the runtime of the rule must be set to `python3.6-lib`\.
- **Note**  
To use the RDKLib, the runtime of the rule must be set to `python3.6-lib`\.


## Evaluation Mode

- **Note**  
Proactive rules do not remediate resources that are flagged as NON\_COMPLIANT or prevent them from being deployed\.


## Custom Rules

- **Note**  
**High Number of Lambda Function Invocations**  
AWS Config Custom Lambda Rules can cause a high number of Lambda function invocations if the rule is not scoped to one or more resource types\. To avoid increased activity associated with your account, provide resources in scope for your Custom Lambda rules\. If no resource types are selected, the rule will invoke the Lambda function for all resources in the account\.


## Managing Your Rules

- **Note**  
AWS Config evaluates only the resource types that it is recording\. For example, if you add the **cloudtrail\-enabled** rule but don't record the CloudTrail trail resource type, AWS Config can't evaluate whether the trails in your account are compliant or noncompliant\. For more information, see [Selecting Which Resources AWS Config Records](select-resources.md)\.
- **Note**  
Proactive rules do not remediate resources that are flagged as NON\_COMPLIANT or prevent them from being deployed\.
- **Note**  
Proactive rules do not remediate resources that are flagged as NON\_COMPLIANT or prevent them from being deployed\.
- **Note**  
For a list of managed rules that support proactive evaluation, see [List of AWS Config Managed Rules by Evaluation Mode](https://docs.aws.amazon.com/config/latest/developerguide/managed-rules-by-evaluation-mode.html)\.
- **Note**  
If a rule is creating evaluation results that are not valid, it is recommended that to delete these results before you fix the rule and run a new evaluation\. For more information, see [Deleting Evaluation Results from AWS Config Rules](deleting-evaluations-results.md)\.
- **Note**  
Proactive rules do not remediate resources that are flagged as NON\_COMPLIANT or prevent them from being deployed\.
- **Note**  
For a list of managed rules that support proactive evaluation, see [List of AWS Config Managed Rules by Evaluation Mode](https://docs.aws.amazon.com/config/latest/developerguide/managed-rules-by-evaluation-mode.html)\.


## Evaluating Your Resources

- **Note**  
Proactive rules do not remediate resources that are flagged as NON\_COMPLIANT or prevent them from being deployed\.
- **Note**  
You can also turn on proactive evaluation using the [http://docs.aws.amazon.com/cli/latest/reference/configservice/put-config-rule.html](http://docs.aws.amazon.com/cli/latest/reference/configservice/put-config-rule.html) command and enabling `PROACTIVE` for `EvaluationModes` or using the [PutConfigRule](https://docs.aws.amazon.com/config/latest/APIReference/API_PutConfigRule.html) action and enabling `PROACTIVE` for `EvaluationModes`\.
- **Note**  
You can re\-evaluate a rule once per minute\. You must wait for AWS Config to complete the evaluation for your rule before you start another evaluation\. You can't run an evaluation if at the same time the rule is being updated or if the rule is being deleted\.


## Managing Organizational Rules

- **Note**  
**For deployments across different regions**  
The API call to deploy rules and conformance packs across accounts is region specific\. At the organization level, you need to change the context of your API call to a different region if you want to deploy rules in other regions\. For example, to deploy a rule in US East \(N\. Virginia\), change the region to US East \(N\. Virginia\) and then call `PutOrganizationConfigRule`\.  
**For accounts within an organization**  
If a new account joins an organization, the rule or conformance pack is deployed to that account\. When an account leaves an organization, the rule or conformance pack is removed\.  
If you deploy an organizational rule or conformance pack in an organization administrator account, and then establish a delegated administrator and deploy an organizational rule or conformance pack in the delegated administrator account, you won't be able to see the organizational rule or conformance pack in the organization administrator account from the delegated administrator account or see the organizational rule or conformance pack in the delegated administrator account from organization administrator account\. The [DescribeOrganizationConfigRules](https://docs.aws.amazon.com/config/latest/APIReference/API_DescribeOrganizationConfigRules.html) and [DescribeOrganizationConformancePacks](https://docs.aws.amazon.com/config/latest/APIReference/API_DescribeOrganizationConformancePacks.html) APIs can only see and interact with the organization\-related resource that were deployed from within the account calling those APIs\.   
**Retry mechanism for new accounts added to an organization**  
Deployment of existing organizational rules and conformance packs will only be retried for 7 hours after an account is added to your organization if a recorder is not available\. You are expected to create a recorder if one doesn't exist within 7 hours of adding an account to your organization\.


## Remediating Noncompliant Resources

- **Note**  
For troubleshooting failed remediation actions, you can run the AWS Command Line Interface command `describe-remediation-execution-status` to get detailed view of a Remediation Execution for a set of resources\. The details include state, timestamps for remediation execution steps, and any error messages for the failed steps\.
- **Note**  
For troubleshooting failed remediation actions, you can run the AWS Command Line Interface command `describe-remediation-execution-status` to get detailed view of a Remediation Execution for a set of resources\. The details include state, timestamps for remediation execution steps, and any error messages for the failed steps\.

