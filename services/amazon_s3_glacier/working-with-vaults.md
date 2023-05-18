---
id: Working with Vaults
title: Working with Vaults
created: 1683841041000
updated: 1683841041000
---
# Working with Vaults

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-glacier-developer-guide.git)
{% endhint %}

## Downloading a Vault Inventory

- **Note**  
The information you get via SNS notification is the same as what you get by calling Describe Job\.


## Configuring Vault Notifications

- **Note**  
Adding a notification configuration to a vault causes S3 Glacier to send a notification each time the event specified in the notification configuration occurs\. You can also optionally specify an Amazon SNS topic in each job initiation request\. If you add both the notification configuration on the vault and also specify an Amazon SNS topic in your initiate job request, S3 Glacier sends both notifications\.
- **Note**  
The Amazon SNS topic must allow the vault to publish a notification\. By default, only the Amazon SNS topic owner can publish a message to the topic\. However, if the Amazon SNS topic and the vault are owned by different AWS accounts, then you must configure the Amazon SNS topic to accept publications from the vault\. You can configure the Amazon SNS topic policy in the Amazon SNS console\.


## Deleting a Vault

- **Note**  
S3 Glacier prepares an inventory for each vault periodically, every 24 hours\. Because the inventory might not reflect the latest information, S3 Glacier ensures the vault is indeed empty by checking if there were any write operations since the last vault inventory\.


## Vault Lock

- **Important**  
After a Vault Lock policy is locked, the policy can no longer be changed or deleted\.
- **Important**  
We recommend that you first create a vault, complete a Vault Lock policy, and then upload your archives to the vault so that the policy will be applied to them\.

