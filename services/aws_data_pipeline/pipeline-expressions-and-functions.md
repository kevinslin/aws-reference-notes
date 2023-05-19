---
id: Pipeline Expressions and Functions
title: Pipeline Expressions and Functions
created: 1683841041000
updated: 1683841041000
---
# Pipeline Expressions and Functions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-data-pipeline-developer-guide.git)
{% endhint %}

## Expressions

- **Note**  
You can create pipelines that have dependencies, such as tasks in your pipeline that depend on the work of other systems or tasks\. If your pipeline requires certain resources, add those dependencies to the pipeline using preconditions that you associate with data nodes and tasks\. This makes your pipelines easier to debug and more resilient\. Additionally, keep your dependencies within a single pipeline when possible, because cross\-pipeline troubleshooting is difficult\.
- **Note**  
The fields preceded by the AT \(@\) sign indicate those fields are runtime fields\.


## Date and Time Functions

- **Note**  
The date/time format for AWS Data Pipeline is Joda Time, which is a replacement for the Java date and time classes\. For more information, see [Joda Time \- Class DateTimeFormat](http://joda-time.sourceforge.net/apidocs/org/joda/time/format/DateTimeFormat.html)\.

