---
id: ETL jobs
title: ETL jobs
created: 1683841041000
updated: 1683841041000
---
# ETL jobs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-glue-developer-guide.git)
{% endhint %}

## Streaming ETL jobs

- **Note**  
AWS Glue bills hourly for streaming ETL jobs while they are running\.
- **Note**  
You can't use the AWS Lake Formation console to create the table; you must use the AWS Glue console\.


## Record matching with FindMatches

- **Note**  
AWS Glue version 2\.0 jobs do not support machine learning transforms\. For more information, see [Running Spark ETL Jobs with Reduced Startup Times](https://docs.aws.amazon.com/glue/latest/dg/reduced-start-times-spark-etl-jobs.html)\.
- **Important**  
Confirm that the IAM role that you pass to AWS Glue has access to the Amazon S3 bucket that contains the labeling file\. By convention, AWS Glue policies grant permission to Amazon S3 buckets or folders whose names are prefixed with **aws\-glue\-**\. If your labeling files are in a different location, add permission to that location in the IAM role\.

