---
id: Monitoring a cluster
title: Monitoring a cluster
created: 1683841041000
updated: 1683841041000
---
# Monitoring a cluster

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-msk-developer-guide.git)
{% endhint %}

## Amazon MSK metrics for monitoring with CloudWatch

- **Important**  
For an Amazon MSK cluster that uses Apache Kafka 2\.4\.1 or a newer version, the metrics in the following table appear only after their values become nonzero for the first time\. For example, to see `BytesInPerSec`, one or more producers must first send data to the cluster\.


## Consumer-lag monitoring

- **Note**  
To turn on consumer\-lag monitoring for a cluster that was created before November 23, 2020, ensure that the cluster is running Apache Kafka 2\.2\.1 or a later version, then [create a support case](https://console.aws.amazon.com/support/home#/)\.

