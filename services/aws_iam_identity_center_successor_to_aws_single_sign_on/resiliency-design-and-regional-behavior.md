---
id: Resiliency design and Regional behavior
title: Resiliency design and Regional behavior
created: 1683841041000
updated: 1683841041000
---
# Resiliency design and Regional behavior

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-single-sign-on-user-guide.git)
{% endhint %}

## Set up emergency access to the AWS Management Console

- **Important**  
We recommend that you deploy this configuration before a disruption occurs because you can't create the configuration if your access to create the required IAM roles is also disrupted\. Also, test this configuration periodically to ensure that your team understands what to do if IAM Identity Center is disrupted\.
- **Note**  
Most IdPs enable you to keep an application integration deactivated until required\. We recommend that you keep the direct IAM federation application deactivated in your IdP until required for emergency access\.

