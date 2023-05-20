---
id: Monitoring AWS services
title: Monitoring AWS services
created: 1683841041000
updated: 1683841041000
---
# Monitoring AWS services

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-chatbot-admin-guide.git)
{% endhint %}

## Tutorial: Creating an Amazon EventBridge rule for AWS Chatbot

- **Note**  
AWS Chatbot only delivers notifications with their original EventBridge event message content to chat channels\. If this message content is modified \(such as by using EventBridge [InputTransformers](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-transform-target-input.html)\), AWS Chatbot won't be able to deliver notifications to your chat channels\.
- **Tip**  
You might create an EventBridge rule that unintentionally sends too many notifications to your chat channels\. This typically happens with EventBridge rules that trigger on API calls via AWS CloudTrail\. To better control the number of notifications you generate, write your EventBridge rules with event pattern based filtering\. For more information about EventBridge event patterns, see [Content\-based filtering in Amazon EventBridge event patterns](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-event-patterns-content-based-filtering.html) in the *EventBridge User Guide*\.

