---
id: Using the Amazon Chime SDK
title: Using the Amazon Chime SDK
created: 1683841041000
updated: 1683841041000
---
# Using the Amazon Chime SDK

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-chime-sdk-developer-guide.git)
{% endhint %}

## Available regions

- **Note**  
Regions marked with an asterisk \(**\***\) must be enabled in your AWS account\. AWS blocks those regions by default\. For more information about enabling regions, see [Enabling a Region](https://docs.aws.amazon.com/general/latest/gr/rande-manage.html) in the *AWS General Reference*\.
- **Note**  
To create a meeting in an AWS GovCloud \(US\) Region, you must use a control region in GovCloud\. Also, control regions in GovCloud can only make meetings in AWS GovCloud \(US\) Regions\.


## SIP integration

- **Note**  
The Amazon Chime SDK recognizes phone numbers only in E\.164 format\. Make sure that an E\.164 phone number is in your `From` header\.


## Amazon Chime SDK event notifications

- **Note**  
If you use the Amazon Chime SDK Meetings namespace, remember that you use a different service principal\. Instead of using the `Chime` service principal, you use `ChimeSDKMeetings`\. For more information about the namespaces, refer to [Migrating to the Amazon Chime SDK Meetings namespace](meeting-namespace-migration.md)\.

