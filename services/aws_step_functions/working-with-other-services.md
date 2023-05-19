---
id: Working with other services
title: Working with other services
created: 1683841041000
updated: 1683841041000
---
# Working with other services

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## AWS SDK service integrations

- **Note**  
The API action will always be camel case, and parameter names will be Pascal case\. For example, you could use Step Functions' `startSyncExecution` API action and specify the parameter `StateMachineArn`\.
- **Note**  
Amazon OpenSearch Service is the successor of the Amazon Elasticsearch service, and we recommend that you use OpenSearch Service for your service integrations\.


## Service Integration Patterns

- **Note**  
Service integrations that use the `.sync` pattern require additional IAM permissions\. For more information, see [IAM Policies for integrated services](service-integration-iam-templates.md)\.
- **Note**  
A task token must contain at least one character, and cannot exceed 1024 characters\.
- **Note**  
You must pass task tokens from principals within the same AWS account\. The tokens won't work if you send them from principals in a different AWS account\.
- **Note**  
To avoid waiting indefinitely if a process fails to send the task token with `SendTaskSuccess` or `SendTaskFailure`, see [Configure a Heartbeat Timeout for a Waiting Task](#wait-token-hearbeat)\.


## Code Snippets

- **Note**  
For more information about specifying service parameters, see [Pass Parameters to a Service API](connect-parameters.md)\.

