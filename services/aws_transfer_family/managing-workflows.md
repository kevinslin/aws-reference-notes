---
id: Managing workflows
title: Managing workflows
created: 1683841041000
updated: 1683841041000
---
# Managing workflows

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-transfer-user-guide.git)
{% endhint %}

## Create a workflow

- **Note**  
Anytime you remove a workflow from a server and replace it with a new one, or update server configuration \(which impacts a workflow's execution role\), you must wait approximately 10 minutes before executing the new workflow\. The Transfer Family server caches the workflow details, and it takes 10 minutes for the server to refresh its cache\.


## Use predefined steps

- **Note**  
Amazon S3 supports buckets and objects, and there is no hierarchy\. However, you can use prefixes and delimiters in object key names to imply a hierarchy and organize your data in a way similar to folders\.
- **Note**  
The `s3:ListBucket` permission is only necessary if you do not select **Overwrite existing**\. This permission checks your bucket to see if a file with the same name already exists\. If you have selected **Overwrite existing**, the workflow doesn't need to check for the file, and can just write it\.
- **Important**  
You must use the `--openpgp` flag in this command\. By default, `gpg` produces encrypted files that do not conform to the [OpenPGP RFC4880](https://www.rfc-editor.org/rfc/rfc4880) standard\. If you don't use this flag, Transfer Family will be unable to decrypt your files\.
- **Note**  
The `s3:ListBucket` permission is only necessary if you do not select **Overwrite existing**\. This permission checks your bucket to see if a file with the same name already exists\. If you have selected **Overwrite existing**, the workflow doesn't need to check for the file, and can just write it\.
- **Note**  
For more details about using files to load parameters, see [ How to load parameters from a file](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-parameters-file.html)\.


## Use custom file-processing steps

- **Note**  
For an example Lambda function, see [Example Lambda function for a custom workflow step](#example-workflow-lambda)\.
- **Note**  
The `previous.file` setting also works differently if you have a predefined step \(tag, copy, decrypt, or delete\) after a custom step\. If the predefined step is configured to use the `previous.file` setting, the predefined step uses the same input file that's used by the custom step\. The processed file from the custom step is not passed to the predefined step\.
- **Note**  
This behavior doesn't occur if you're using Amazon EFS because Amazon EFS doesn't use entity tags to identify files\.


## Monitor workflow execution

- **Note**  
 The 16\-digit alphanumeric identifiers listed in this example are fictitious\. The values that you see in Amazon CloudWatch are different\.


## Workflow decrypt tutorial

- **Note**  
As part of creating an execution role, make sure to establish a trust relationship between the execution role and Transfer Family, as described in [To establish a trust relationship](requirements-roles.md#establish-trust-transfer)\.
- **Note**  
Not every workflow requires every permission listed in this example\. You can limit permissions based on the types of steps in your specific workflow\. The permissions needed for each predefined step type are described in [Use predefined steps](nominal-steps-workflow.md)\. The permissions needed for a custom step are described in [IAM permissions for a custom step](custom-step-details.md#custom-step-iam)\.

