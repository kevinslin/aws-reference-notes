---
id: Using Amazon Chime SDK messaging
title: Using Amazon Chime SDK messaging
created: 1683841041000
updated: 1683841041000
---
# Using Amazon Chime SDK messaging

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-chime-sdk-developer-guide.git)
{% endhint %}

## Understanding authorization by role

- **Note**  
A moderator who is an `AppInstanceAdmin` can perform actions on channels allowed by that role\.
- **Note**  
A member who is an `AppInstanceAdmin` or `ChannelModerator` can perform actions on Channels allowed by those two roles\.
- **Note**  
A non\-member who is an `AppInstanceAdmin` or `ChannelModerator` can perform channel related actions allowed by those two roles\.


## Using elastic channels to host live events

- **Note**  
 Elastic channels don't support hidden memberships, membership preferences, and read message timestamps\.


## Using channel flows to process messages

- **Note**  
Channel flows don't process Control or System messages\. For more information about the message types provided by Amazon Chime SDK Messaging, refer to [Message types](msg-types.md)\.


## Managing message retention

- **Note**  
During the 30\-day grace period, if you the extend the retention policy, or you turn it off, messages that haven't passed the new retention period become visible again to the users in the account\.

