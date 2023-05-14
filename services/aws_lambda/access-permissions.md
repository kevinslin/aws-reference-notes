---
id: Access permissions
title: Access permissions
created: 1683841041000
updated: 1683841041000
---
# Access permissions
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}
## Execution role

- **Note**  
Lambda automatically assumes your execution role when you invoke your function\. You should avoid calling `sts:AssumeRole` manually in your function code\. If your use case requires that the role assumes itself, you must include the role itself as a trusted principal in your role's trust policy\. For more information on how to modify a role trust policy, see [ Modifying a role trust policy \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-managingrole-editing-console.html#roles-managingrole_edit-trust-policy) in the IAM User Guide\.
- **Note**  
You cannot use the `lambda:SourceFunctionArn` condition key in resource\-based policies\.
- **Note**  
The `lambda:SourceFunctionArn` condition key is different from the `lambda:FunctionArn` and `aws:SourceArn` condition keys\. The `lambda:FunctionArn` condition key applies only to [event source mappings](invocation-eventsourcemapping.md) and helps define which functions your event source can invoke\. The `aws:SourceArn` condition key applies only to policies where your Lambda function is the target resource, and helps define which other AWS services and resources can invoke that function\. The `lambda:SourceFunctionArn` condition key can apply to any identity\-based policy or SCP to define the specific Lambda functions that have permissions to make specific AWS API calls to other resources\.


## User policies

- **Note**  
The AWS managed policies **AWSLambdaFullAccess** and **AWSLambdaReadOnlyAccess** will be [deprecated](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-deprecated.html) on March 1, 2021\. After this date, you cannot attach these policies to new IAM users\. For more information, see the related [troubleshooting topic](security_iam_troubleshoot.md#security_iam_troubleshoot-admin-deprecation)\.
- **Note**  
For a function defined as a container image, the user permission to access the image MUST be configured in the Amazon Elastic Container Registry For an example, see [Amazon ECR permissions\.](gettingstarted-images.md#configuration-images-permissions)


## Control access using tags

- **Note**  
Do not use the `ResourceTag` condition key in a policy with the `iam:PassRole` action\. You cannot use the tag on an IAM role to control access to who can pass that role\. For more information about permissions required to pass a role to a service, see [Granting a user permissions to pass a role to an AWS service](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_passrole.html)\.


## Resource-based policies

- **Note**  
You can only update resource\-based policies for Lambda resources within the scope of the [AddPermission](API_AddPermission.md) and [AddLayerVersionPermission](API_AddLayerVersionPermission.md) API actions\. Currently, you can't author policies for your Lambda resources in JSON, or use conditions that don't map to parameters for those actions\.
- **Note**  
When you add a trigger to your function with the Lambda console, the console updates the function's resource\-based policy to allow the service to invoke it\. To grant permissions to other accounts or services that aren't available in the Lambda console, you can use the AWS CLI\.
- **Note**  
In this command, `Principal` is `*`\. This means that all users in the organization `o-a1b2c3d4e5f` get function invocation permissions\. If you specify an AWS account or role as the `Principal`, then only that principal gets function invocation permissions, but only if they are also part of the `o-a1b2c3d4e5f` organization\.


## Resources and conditions

- **Note**  
You can't use a wildcard character \(\*\) to match the account ID\. For more information on accepted syntax, see [IAM JSON policy reference](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html) in the *IAM User Guide*\.
- **Note**  
The [GetLayerVersion](API_GetLayerVersion.md) action also covers [GetLayerVersionByArn](API_GetLayerVersionByArn.md)\. Lambda does not support `GetLayerVersionByArn` as an IAM action\.

