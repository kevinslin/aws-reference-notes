---
id: Supported actions
title: Supported actions
created: 1683841041000
updated: 1683841041000
---
# Supported actions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-events-developer-guide.git)
{% endhint %}

## Working with other AWS services

- **Important**  
You must choose the same AWS Region for both AWS IoT Events and the AWS services to work with\. For the list of supported Regions, see [AWS IoT Events endpoints and quotas](https://docs.aws.amazon.com/general/latest/gr/iot-events.html) in the *Amazon Web Services General Reference*\.
You must use the same AWS Region when you create other AWS resources for the AWS IoT Events actions\. If you switch AWS Regions, you might have issues accessing the AWS resources\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `iot:Publish` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `iotevents:BatchPutMessage` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Important**  
To receive the data, you must use an existing asset property in AWS IoT SiteWise\.  
If you use the AWS IoT Events console, you must specify `propertyAlias` to identify the target asset property\.
If you use the AWS CLI, you must specify either `propertyAlias` or both `assetId` and `propertyId` to identify the target asset property\.
For more information, see [Mapping industrial data streams to asset properties](https://docs.aws.amazon.com/iot-sitewise/latest/userguide/connect-data-streams.html) in the *AWS IoT SiteWise User Guide*\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `iotsitewise:BatchPutAssetPropertyValue` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `dynamodb:PutItem` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `dynamodb:PutItem` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `firehose:PutRecord` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `lambda:InvokeFunction` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
The Amazon SNS topic publish action doesn't support [Amazon SNS FIFO \(first in, first out\) topics](https://docs.aws.amazon.com/sns/latest/dg/sns-fifo-topics.html)\. Because the rules engine is a fully distributed service, the messages may not display in a specified order when the Amazon SNS action is initiated\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `sns:Publish` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
The Amazon SQS action doesn't support [Amazon SQS FIFO \(first in, first out\) topics](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/FIFO-queues.html)\. Because the rules engine is a fully distributed service, the messages may not display in a specified order when the  Amazon SQS action is initiated\.
- **Note**  
Make sure that the policy attached to your AWS IoT Events service role grants the `sqs:SendMessage` permission\. For more information, see [Identity and access management for AWS IoT Events](security-iam.md)\.
- **Note**  
To collect and process large streams of data records in real time, you can use other AWS services, such as [Amazon Kinesis](https://docs.aws.amazon.com/kinesis/index.html)\. From there, you can complete an initial analysis and then send the results to AWS IoT Events as an input to a detector\.

