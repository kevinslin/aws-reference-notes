---
id: Logging and monitoring
title: Logging and monitoring
created: 1683841041000
updated: 1683841041000
---
# Logging and monitoring

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## Logging AWS Control Tower Actions with AWS CloudTrail

- **Note**  
In AWS Control Tower releases before landing zone version 3\.0, AWS Control Tower created a member account trail\. When you update to release 3\.0, your CloudTrail trail is updated to become an organization trail\. For best practices when moving between trails, see [Creating an organizational trail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/creating-trail-organization.html#creating-an-organizational-trail-best-practice) in the CloudTrail User Guide\.


## Monitoring resource changes with AWS Config

- **Note**  
 **If your landing zone version is 3\.0 or later**: AWS Control Tower limits AWS Config recording for global resources, such as IAM users, groups, roles, and customer\-managed polices, to your home Region only\. Therefore, some of the information in this section may not apply to your landing zone\.
- **Note**  
When AWS Control Tower works with AWS Config, a Region may be governed by AWS Control Tower, or ungoverned, and AWS Config still records the changes if the account operates in that Region\.
- **Note**  
After you unenroll the account, AWS Control Tower cannot enforce detective controls or log account events, such as AWS Config activities, for resources in that account\.

