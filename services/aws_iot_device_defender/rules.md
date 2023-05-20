---
id: Rules
title: Rules
created: 1683841041000
updated: 1683841041000
---
# Rules

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Pass role permissions

- **Note**  
Lambda functions use resource\-based policy, where the policy is attached directly to the Lambda function itself\. When you create a rule that invokes a Lambda function, you do not pass a role, so the user creating the rule does not need the `iam:PassRole` permission\. For more information about Lambda function authorization, see [Granting Permissions Using a Resource Policy](https://docs.aws.amazon.com/lambda/latest/dg/intro-permission-model.html#intro-permission-model-access-policy)\.


## Creating an AWS IoT rule

- **Note**  
Creating and updating rules are administrator\-level actions\. Any user who has permission to create or update rules is able to access data processed by the rules\.


## Accessing cross-account resources using AWS IoT rules

- **Note**  
You must define the rule in the same AWS Region as another service's resource, so that the rule action can interact with that resource\. For more information about AWS IoT rule actions, see [AWS IoT rule actions](iot-rule-actions.md)\.


## AWS IoT SQL reference

- **Note**  
Comments are not currently supported in AWS IoT SQL syntax\.  
Attribute names with spaces in them can't be used as field names in the SQL statement\. While the incoming payload can have attribute names with spaces in them, such names can't be used in the SQL statement\. They will, however, be passed through to the outgoing payload if you use a wildcard \(\*\) field name specification\.

