---
id: MSK Connect
title: MSK Connect
created: 1683841041000
updated: 1683841041000
---
# MSK Connect

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-msk-developer-guide.git)
{% endhint %}

## Workers

- **Note**  
If you specify an offset storage topic when you create a *sink* connector, MSK Connect creates the topic if it does not already exist\. However, the topic will not be used to store connector offsets\.   
Sink connector offsets are instead managed using the Kafka consumer group protocol\. Each sink connector creates a group named `connect-{CONNECTOR_NAME}`\. As long as the consumer group exists, any successive sink connectors that you create with the same `CONNECTOR_NAME` value will continue from the last committed offset\.
- **Important**  
You must give your new connector the same name as the old connector\.


## Logging

- **Note**  
Sensitive configuration values can appear in connector logs if a plugin does not define those values as secret\. Kafka Connect treats undefined configuration values the same as any other plaintext value\.

