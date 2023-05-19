---
id: Understanding AWS Snowball Edge Jobs
title: Understanding AWS Snowball Edge Jobs
created: 1683841041000
updated: 1683841041000
---
# Understanding AWS Snowball Edge Jobs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-snowball-developer-guide.git)
{% endhint %}

## Importing Jobs into Amazon S3

- **Important**  
Don't delete your local copies of the transferred data until you can verify the results of the job completion report and review your import logs\.


## Exporting Jobs from Amazon S3

- **Note**  
Tags and metadata are NOT currently supported, in other words, all tags and metadata would be removed when exporting objects from S3 buckets\.
- **Important**  
Data you want to export to a Snow device must be in Amazon S3\. Any data in Amazon S3 Glacier that you plan to export to the Snow device will have to be thawed or moved into the S3 storage class before it can be exported\. Do this before creating the Snow export job\.  
Don't change, update, or delete the exported Amazon S3 objects until you can verify that all of your contents for the entire job have been copied to your on\-premises data destination\.


## Cloning a Job in the Console

- **Note**  
Cloning a job is a shortcut available in the console to make creating additional jobs easier\. If you're creating jobs with the job management API, you can simply run the job creation command again\.

