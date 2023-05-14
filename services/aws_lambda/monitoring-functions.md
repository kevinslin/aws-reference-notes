---
id: Monitoring functions
title: Monitoring functions
created: 1683841041000
updated: 1683841041000
---
# Monitoring functions
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}
## Function metrics

- **Note**  
The timestamp on a metric reflects when the function was invoked\. Depending on the duration of the invocation, this can be several minutes before the metric is emitted\. For example, if your function has a 10\-minute timeout, look more than 10 minutes in the past for accurate metrics\.


## Function logs

- **Note**  
It may take 5 to 10 minutes for logs to show up after a function invocation\.


## AWS X-Ray

- **Note**  
X\-Ray tracing is currently not supported for Lambda functions with Amazon Managed Streaming for Apache Kafka \(Amazon MSK\), self\-managed Apache Kafka, or Amazon MQ with ActiveMQ and RabbitMQ event source mappings\.
- **Note**  
You cannot configure the X\-Ray sampling rate for your functions\.
- **Note**  
If your Lambda function uses [provisioned concurrency](provisioned-concurrency.md), your X\-Ray trace might display a function initialization with a very long duration\.   
Provisioned concurrency initializes function instances in advance, to reduce lag at the time of invocation\. Over time, provisioned concurrency refreshes these instances by creating new instances to replace the old ones\. For workloads with steady traffic, the new instances are initialized well in advance of their first invocation\. The time gap gets recorded in the X\-Ray trace as the initialization duration\.
- **Important**  
In Lambda, you can use the X\-Ray SDK to extend the `Invocation` subsegment with additional subsegments for downstream calls, annotations, and metadata\. You can't access the function segment directly or record work done outside of the handler invocation scope\.


## Code profiler

- **Note**  
When you deactivate CodeGuru Profiler from the console, Lambda automatically removes the CodeGuru Profiler layer and environment variables from your function\. However, Lambda does not remove the `AmazonCodeGuruProfilerAgentAccess` policy from your execution role\.

