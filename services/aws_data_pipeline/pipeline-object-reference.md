---
id: Pipeline Object Reference
title: Pipeline Object Reference
created: 1683841041000
updated: 1683841041000
---
# Pipeline Object Reference

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-data-pipeline-developer-guide.git)
{% endhint %}

## Schedule

- **Note**  
When a schedule's start time is in the past, AWS Data Pipeline backfills your pipeline and begins scheduling runs immediately beginning at the specified start time\. For testing/development, use a relatively short interval\. Otherwise, AWS Data Pipeline attempts to queue and schedule all runs of your pipeline for that interval\. AWS Data Pipeline attempts to prevent accidental backfills if the pipeline component `scheduledStartTime` is earlier than 1 day ago by blocking pipeline activation\.

