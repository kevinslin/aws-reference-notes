---
id: Integrating other services
title: Integrating other services
created: 1683841041000
updated: 1683841041000
---
# Integrating other services
## API Gateway

- **Note**  
If your function and API are in different regions, the region identifier in the source ARN must match the region of the function, not the region of the API\. When API Gateway invokes a function, it uses a resource ARN that is based on the ARN of the API, but modified to match the function's region\.
- **Note**  
API Gateway does not retry any Lambda invocations\. If Lambda returns an error, API Gateway returns an error response to the client\.


## EventBridge (CloudWatch Events)

- **Note**  
Amazon EventBridge is the preferred way to manage your events\. CloudWatch Events and EventBridge are the same underlying service and API, but EventBridge provides more features\. Changes you make in either CloudWatch Events or EventBridge will appear in each console\. For more information, see the [Amazon EventBridge documentation](https://docs.aws.amazon.com/eventbridge/index.html)\.


## CloudFront (Lambda@Edge)

- **Note**  
Lambda@Edge supports a limited set of runtimes and features\. For details, see [Requirements and restrictions on Lambda functions](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/lambda-requirements-limits.html) in the Amazon CloudFront developer guide\.


## DynamoDB

- **Note**  
You are not charged for GetRecords API calls invoked by Lambda as part of DynamoDB triggers\.
- **Note**  
For Java functions, we recommend using a `Map<String, String>` to represent the state\.
- **Note**  
If the `batchItemFailures` array contains multiple items, Lambda uses the record with the lowest sequence number as the checkpoint\. Lambda then retries all records starting from that checkpoint\.


## ElastiCache

- **Note**  
On Windows, some Bash CLI commands that you commonly use with Lambda \(such as `zip`\) are not supported by the operating system's built\-in terminals\. To get a Windows\-integrated version of Ubuntu and Bash, [install the Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)\.


## EFS

- **Note**  
To configure a function to connect to a file system, see [Configuring file system access for Lambda functions](configuration-filesystem.md)\.
- **Note**  
If you use [provisioned concurrency](configuration-concurrency.md), your function can consume burst credits even when idle\. With provisioned concurrency, Lambda initializes instances of your function before it is invoked, and recycles instances every few hours\. If you use files on an attached file system during initialization, this activity can use all of your burst credits\.


## Apache Kafka

- **Note**  
Lambda supports the [PBES1](https://datatracker.ietf.org/doc/html/rfc2898/#section-6.1) \(but not PBES2\) private key encryption algorithms\.
- **Note**  
While Lambda functions typically have a maximum timeout limit of 15 minutes, event source mappings for Amazon MSK, self\-managed Apache Kafka, and Amazon MQ for ActiveMQ and RabbitMQ only support functions with maximum timeout limits of 14 minutes\. This constraint ensures that the event source mapping can properly handle function errors and retries\.
- **Note**  
If your Lambda event records exceed the allowed size limit of 6 MB, they can go unprocessed\.


## Kinesis Streams

- **Note**  
Kinesis charges for each shard and, for enhanced fan\-out, data read from the stream\. For pricing details, see [Amazon Kinesis pricing](https://aws.amazon.com/kinesis/data-streams/pricing)\.
- **Note**  
For Java functions, we recommend using a `Map<String, String>` to represent the state\.
- **Note**  
If the `batchItemFailures` array contains multiple items, Lambda uses the record with the lowest sequence number as the checkpoint\. Lambda then retries all records starting from that checkpoint\.


## MQ

- **Note**  
By default, Amazon MQ has a weekly maintenance window for brokers\. During that window of time, brokers are unavailable\. For brokers without standby, Lambda cannot process any messages during that window\.
- **Note**  
While Lambda functions typically have a maximum timeout limit of 15 minutes, event source mappings for Amazon MSK, self\-managed Apache Kafka, and Amazon MQ for ActiveMQ and RabbitMQ only support functions with maximum timeout limits of 14 minutes\. This constraint ensures that the event source mapping can properly handle function errors and retries\.
- **Note**  
When using an encrypted customer managed key, add the `[kms:Decrypt](https://docs.aws.amazon.com/msk/1.0/apireference/clusters-clusterarn-bootstrap-brokers.html#clusters-clusterarn-bootstrap-brokersget)` permission as well\.
- **Note**  
Lambda does not support custom redelivery policies\. Instead, Lambda uses a policy with the default values from the [Redelivery Policy](https://activemq.apache.org/redelivery-policy) page on the Apache ActiveMQ website, with `maximumRedeliveries` set to 5\.


## MSK

- **Note**  
While Lambda functions typically have a maximum timeout limit of 15 minutes, event source mappings for Amazon MSK, self\-managed Apache Kafka, and Amazon MQ for ActiveMQ and RabbitMQ only support functions with maximum timeout limits of 14 minutes\. This constraint ensures that the event source mapping can properly handle function errors and retries\.
- **Note**  
Lambda supports the [PBES1](https://datatracker.ietf.org/doc/html/rfc2898/#section-6.1) \(but not PBES2\) private key encryption algorithms\.
- **Note**  
If Lambda can't connect to the most secure broker type, Lambda doesn't attempt to connect to a different \(weaker\) broker type\. If you want Lambda to choose a weaker broker type, deactivate all stronger auth methods on your cluster\.
- **Note**  
Lambda eventually plans to remove the `kafka:DescribeCluster` permission from this policy\. You should migrate any applications using `kafka:DescribeCluster` to use `kafka:DescribeClusterV2` instead\.
- **Note**  
Your Amazon VPC configuration is discoverable through the [Amazon MSK API](https://docs.aws.amazon.com/msk/1.0/apireference/resources.html)\. You don't need to configure it during setup using the create\-event\-source\-mapping command\.


## SQS

- **Note**  
If you're using a batch window and your SQS queue contains very low traffic, Lambda might wait for up to 20 seconds before invoking your function\. This is true even if you set a batch window lower than 20 seconds\.
- **Note**  
Make sure that you configure the dead\-letter queue on the source queue, not on the Lambda function\. The dead\-letter queue that you configure on a function is used for the function's [asynchronous invocation queue](invocation-async.md), not for event source queues\.
- **Note**  
Amazon SQS has a perpetual free tier for requests\. Beyond the free tier, Amazon SQS charges per million requests\. While your event source mapping is active, Lambda makes requests to the queue to get items\. For pricing details, see [Amazon SQS pricing](http://aws.amazon.com/sqs/pricing)\.
- **Note**  
If you're using this feature with a FIFO queue, your function should stop processing messages after the first failure and return all failed and unprocessed messages in `batchItemFailures`\. This helps preserve the ordering of messages in your queue\.

