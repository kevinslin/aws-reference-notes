---
id: AWS IoT Device Defender
title: AWS IoT Device Defender
created: 1683841041000
updated: 1683841041000
---
# AWS IoT Device Defender

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Detect

- **Important**  
Messages reported by devices are rejected if the thing name contains control characters or if the thing name is longer than 128 bytes of UTF\-8 encoded characters\.


## Mitigation actions

- **Note**  
Mitigation actions won't be performed on suppressed audit findings\. For more information about audit finding suppressions, see [Audit finding suppressions](audit-finding-suppressions.md)\.
- **Important**  
Applying mitigation actions that change certificates, add things to a new thing group, or replace the policy can have an impact on your devices and applications\. For example, devices might be unable to connect\. Consider the implications of the mitigation actions before you apply them\. You might need to take other actions to correct the problems before your devices and applications can function normally\. For example, you might need to provide updated device certificates\. Mitigation actions can help you quickly limit your risk, but you must still take corrective actions to address the underlying issues\.


## Using AWS IoT Device Defender with other AWS services

- **Note**  
The fleet indexing feature to support indexing AWS IoT Device Defender violations data is in preview release for AWS IoT Device Management and is subject to change\.

