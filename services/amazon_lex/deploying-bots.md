---
id: Deploying Bots
title: Deploying Bots
created: 1683841041000
updated: 1683841041000
---
# Deploying Bots

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-lex-developer-guide.git)
{% endhint %}

## Deploying an Amazon Lex Bot on a Messaging Platform

- **Note**  
When storing your Facebook, Slack, or Twilio configurations, Amazon Lex uses AWS Key Management Service customer master keys \(CMK\) to encrypt the information\. The first time that you create a channel to one of these messaging platforms, Amazon Lex creates a default CMK \(`aws/lex`\)\. Alternatively, you can create your own CMK with AWS KMS\. This gives you more flexibility, including the ability to create, rotate, and disable keys\. You can also define access controls and audit the encryption keys used to protect your data\. For more information, see the [AWS Key Management Service Developer Guide](http://docs.aws.amazon.com/kms/latest/developerguide/)\.

