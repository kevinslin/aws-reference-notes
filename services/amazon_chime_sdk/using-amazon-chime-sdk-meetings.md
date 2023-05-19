---
id: Using Amazon Chime SDK meetings
title: Using Amazon Chime SDK meetings
created: 1683841041000
updated: 1683841041000
---
# Using Amazon Chime SDK meetings

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-chime-sdk-developer-guide.git)
{% endhint %}

## Using meeting Regions

- **Note**  
We recommend that you always specify a value in the `MediaRegion` parameter in the [CreateMeeting](https://docs.aws.amazon.com/chime-sdk/latest/APIReference/API_CreateMeeting.html) API action\. For more information about the Regions, refer to [Available regions](sdk-available-regions.md)\.


## Network configuration

- **Note**  
When you configure your network, you must enable Extention Mechanisms for DNS \(EDNS0\) by default\. This enables your application to reach the Amazon Chime SDK services by ensuring that host information is the correct size for UDP packets\.


## Creating Amazon Chime SDK media pipelines

- **Important**  
You and your end users must understand that recording Amazon Chime SDK meetings may be subject to laws or regulations regarding the recording of electronic communications\. It is your and your end users’ responsibility to comply with all applicable laws regarding the recordings, including properly notifying all participants in a recorded session that the session or communication is being recorded, and obtain their consent\.   
You and your end users are responsible for all content streaming using the media live connector service, and must ensure that such content does not violate the law, infringe or misappropriate the rights of any third party, or otherwise violate a material term of your agreement with Amazon\.
- **Note**  
If you exceed the limit for any Region, the [CreateMediaCapturePipeline](https://docs.aws.amazon.com/chime-sdk/latest/APIReference/API_media-pipelines-chime_CreateMediaCapturePipeline.html), [CreateMediaConcatenationPipeline](https://docs.aws.amazon.com/chime-sdk/latest/APIReference/API_media-pipelines-chime_CreateMediaConcatenationPipeline.html), and [CreateMediaLiveConnectorPipeline](https://docs.aws.amazon.com/chime-sdk/latest/APIReference/API_media-pipelines-chime_CreateMediaLiveConnectorPipeline.html) APIs will throw **Resource Limit Exceeded** exceptions\.  
You can use the **Service Quotas** page in the AWS console to adjust your active pipeline limits, or you can contact your [customer support representative](https://docs.aws.amazon.com/awssupport/latest/user/getting-started.html)\. For more information about the Amazon Chime SDK meeting limits, see [Amazon Chime SDK service quotas](meetings-sdk.md#mtg-limits)\.


## Using Amazon Chime SDK live transcription

- **Important**  
Amazon Chime SDK live transcription is powered by Amazon Transcribe\. Use of Amazon Transcribe is subject to the [AWS Service Terms](https://aws.amazon.com/service-terms/), including the terms specific to the AWS Machine Learning and Artificial Intelligence Services\.


## Using media replication

- **Note**  
The service quota *Chime SDK Meetings \- replica meetings per primary meeting* has a default value of 4, and you can increase that limit on request\. For more information about quotas, refer to [AWS service quotas](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html) in the *AWS General Reference*\.

