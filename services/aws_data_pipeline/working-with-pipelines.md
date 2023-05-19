---
id: Working with Pipelines
title: Working with Pipelines
created: 1683841041000
updated: 1683841041000
---
# Working with Pipelines

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-data-pipeline-developer-guide.git)
{% endhint %}

## Scheduling Pipelines

- **Note**  
You can find the Default object on the Architect page in the **Other** section\.
- **Note**  
The minimum scheduling interval is 15 minutes\.
- **Note**  
You can find the Default object on the Architect page in the **Other** section\.


## Cloning Your Pipeline

- **Note**  
You can't clone a pipeline using the command line interface \(CLI\)\.


## Deleting Your Pipeline

- **Important**  
You can't restore a pipeline after you delete it, so be sure that you won't need the pipeline in the future before you delete it\.


## Staging Data and Tables with Activities

- **Note**  
Staging only functions when the `stage` field is set to `true` on an activity, such as `ShellCommandActivity`\. For more information, see [ShellCommandActivity](dp-object-shellcommandactivity.md)\.
- **Note**  
 This scenario only works as described if your data inputs and outputs are `S3DataNode` objects\. Additionally, output data staging is allowed only when `directoryPath` is set on the output `S3DataNode` object\.
- **Note**  
 This scenario only works as described if your data inputs and outputs are `S3DataNode` or `MySqlDataNode` objects\. Table staging is not supported for `DynamoDBDataNode`\.
- **Note**  
In this example, the table name variable has the \# \(hash\) character prefix because AWS Data Pipeline uses expressions to access the `tableName` or `directoryPath`\. For more information about how expression evaluation works in AWS Data Pipeline, see [Expression Evaluation](dp-pipeline-expressions.md#dp-datatype-functions)\.


## Using Resources in Multiple Regions

- **Note**  
The following list includes regions in which AWS Data Pipeline can orchestrate workflows and launch Amazon EMR or Amazon EC2 resources\. AWS Data Pipeline may not be supported in these regions\. For information about regions in which AWS Data Pipeline is supported, see [AWS Regions and Endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html#datapipeline_region)\.


## Pipeline Definition File Syntax

- **Note**  
On user\-defined fields, AWS Data Pipeline only checks for valid references to other pipeline components, not any custom field string values that you add\.


## Working with the API

- **Note**  
 If you are not writing programs that interact with AWS Data Pipeline, you do not need to install any of the AWS SDKs\. You can create and run pipelines using the console or command\-line interface\. For more information, see [Setting up for AWS Data Pipeline](dp-get-setup.md)

