---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-dms-user-guide.git)
{% endhint %}

## Identity and access management

- **Note**  
You can further restrict access to AWS DMS resources using tagging\. For more information about restricting access to AWS DMS resources using tagging, see [Fine\-grained access control using resource names and tags](CHAP_Security.FineGrainedAccess.md)\.
- **Note**  
If you use the AWS DMS console for your database migration, these roles are added to your AWS account automatically\.


## Using SSL

- **Note**  
The SSL Mode option on the DMS console or API doesn’t apply to some data streaming and NoSQL services like Kinesis, and DynamoDB\. They are secure by default, so DMS shows the SSL mode setting is equal to none \(**SSL Mode=None**\)\. You don’t need to provide any additional configuration for your endpoint to make use of SSL\. For example, when using Kinesis as a target endpoint, it is secure by default\. All API calls to Kinesis use SSL, so there is no need for an additional SSL option in the DMS endpoint\. You can securely put data and retrieve data through SSL endpoints using the HTTPS protocol, which DMS uses by default when connecting to a Kinesis Data Stream\.

