---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-events-developer-guide.git)
{% endhint %}

## Simple step-by-step example

- **Note**  
When you create a detector model or update an existing one, it takes several minutes before the new or updated detector model begins to receive messages and create detectors \(instances\)\. If you update the detector model, during this time you might continue to see behavior based on the previous version\.
- **Note**  
You can send multiple messages at one time with `BatchPutMessage`\. However, the order in which these messages are processed isn't guaranteed\. To guarantee messages \(inputs\) are processed in order, send them one at a time and wait for a successful response each time the API is called\.

