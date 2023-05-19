---
id: Managing data ingestion
title: Managing data ingestion
created: 1683841041000
updated: 1683841041000
---
# Managing data ingestion

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-sitewise-user-guide.git)
{% endhint %}

## Managing data streams

- **Note**  
An asset property can't be associated with multiple data streams at the same time\.
- **Note**  
If you're new to AWS IoT SiteWise after November 24, 2021, you can skip this section\.
- **Important**  
Before you ingest data to a data stream, do the following\.  
The `timeseries` resource must be authorized if you use a property alias to identify the data stream\.
The `asset` resource must be authorized if you use an asset ID to identify the asset that contains the associated asset property\.

