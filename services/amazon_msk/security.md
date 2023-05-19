---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-msk-developer-guide.git)
{% endhint %}

## Changing security groups

- **Important**  
If you change the security group that is associated with the brokers of a cluster, and then add new brokers to that cluster, Amazon MSK associates the new brokers with the original security group that was associated with the cluster when the cluster was created\. However, for a cluster to work correctly, all of its brokers must be associated with the same security group\. Therefore, if you add new brokers after changing the security group, you must follow the previous procedure again and update the ENIs of the new brokers\.


## Controlling access to Apache ZooKeeper

- **Note**  
The names of the parameters you use in your Apache ZooKeeper configuration file and those you use in your `KAFKA_OPTS` environment variable are not consistent\. Pay attention to which names you use with which parameters in your configuration file and `KAFKA_OPTS` environment variable\.


## Logging

- **Note**  
Amazon MSK does not support delivering broker logs to Kinesis Data Firehose in the Asia Pacific \(Osaka\) Region\.
- **Note**  
By default, when broker logging is enabled, Amazon MSK logs `INFO` level logs to the specified destinations\. However, users of Apache Kafka 2\.4\.X and later can dynamically set the broker log level to any of the [log4j log levels](https://logging.apache.org/log4j/1.2/apidocs/org/apache/log4j/Level.html)\. For information about dynamically setting the broker log level, see [ KIP\-412: Extend Admin API to support dynamic application log levels](https://cwiki.apache.org/confluence/display/KAFKA/KIP-412%3A+Extend+Admin+API+to+support+dynamic+application+log+levels)\. If you dynamically set the log level to `DEBUG` or `TRACE`, we recommend using Amazon S3 or Kinesis Data Firehose as the log destination\. If you use CloudWatch Logs as a log destination and you dynamically enable `DEBUG` or `TRACE` level logging, Amazon MSK may continuously deliver a sample of logs\. This can significantly impact broker performance and should only be used when the `INFO` log level is not verbose enough to determine the root cause of an issue\.
- **Note**  
AWS CloudTrail logs are available for Amazon MSK only when you use [IAM access control](iam-access-control.md)\.

