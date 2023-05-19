---
id: Monitoring data with alarms
title: Monitoring data with alarms
created: 1683841041000
updated: 1683841041000
---
# Monitoring data with alarms

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-sitewise-user-guide.git)
{% endhint %}

## Configuring alarms on assets

- **Note**  
You can configure these values for AWS IoT Events alarms, but not external alarms\.


## Responding to alarms

- **Note**  
You can respond to AWS IoT Events alarms, but not external alarms\.
- **Note**  
You must enable the acknowledge flow on the alarm so that you can acknowledge the alarm\. This option is enabled by default if you define the alarm from the AWS IoT SiteWise console\.


## Ingesting external alarm state

- **Note**  
If your data source can't report data in this format, or you can't convert your data to this format before you ingest it, you might choose not to use an alarm property\. Instead, you can ingest the data as a measurement property with the string data type, for example\. For more information, see [Defining data streams from equipment \(measurements\)](measurements.md) and [Ingesting data to AWS IoT SiteWise](industrial-data-ingestion.md)\.

