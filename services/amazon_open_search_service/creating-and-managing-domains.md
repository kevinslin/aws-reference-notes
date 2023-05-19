---
id: Creating and managing domains
title: Creating and managing domains
created: 1683841041000
updated: 1683841041000
---
# Creating and managing domains

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-opensearch-service-developer-guide.git)
{% endhint %}

## Configuration changes

- **Important**  
You do *not* incur any additional charges during configuration changes and service maintenance\. You're billed only for the number of nodes that you request for your cluster\. For specifics, see [Charges for configuration changes](#managedomains-config-charges)\.


## Service software updates

- **Note**  
For explanations of the changes and additions made in each *major* \(non\-patch\) service software update, see the [release notes](release-notes.md)\.
- **Tip**  
After you request an update, you have a narrow window of time in which you can cancel it\. The duration of this `PENDING_UPDATE` state can vary greatly and depends on your AWS Region and the number of concurrent updates that OpenSearch Service is performing\. To cancel an update, use the console or `cancel-service-software-update` AWS CLI command\.


## Off-peak windows

- **Note**  
Off\-peak windows were introduced on February 16, 2023\. All domains created before this date have the off\-peak window disabled by default\. You must manually enable and configure the off\-peak window for these domains\. All domains created *after* this date will have the off\-peak window enabled by default\. You can't disable the off\-peak window for a domain after it's enabled\.
- **Note**  
OpenSearch Service can schedule the action within an hour of the time you select\. For exmple, if you choose to apply an update at 5 P\.M\., it can be applied between 5 and 6 P\.M\.
- **Note**  
You can't revert back to using maintenance windows after you migrate your domain to use off\-peak windows\.


## Configuring a multi-AZ domain

- **Note**  
OpenSearch Service manages Multi\-AZ domains transparently, so you can't manually simulate Availability Zone disruptions\.


## VPC support

- **Note**  
If you place your OpenSearch Service domain within a VPC, your computer must be able to connect to the VPC\. This connection often takes the form of a VPN, transit gateway, managed network, or proxy server\. You can't directly access your domains from outside the VPC\.
- **Note**  
OpenSearch Service doesn't support IPv6 addresses with a VPC\. You can use a VPC that has IPv6 enabled, but the domain will use IPv4 addresses\.
- **Note**  
Because security groups already enforce IP\-based access policies, you can't apply IP\-based access policies to OpenSearch Service domains that reside within a VPC\. If you use public access, IP\-based policies are still available\.
- **Tip**  
We recommend that you create dedicated subnets for the OpenSearch Service reserved IP addresses\. By using dedicated subnets, you avoid overlap with other applications and services and ensure that you can reserve additional IP addresses if you need to scale your cluster in the future\. To learn more, see [Creating a subnet in your VPC](https://docs.aws.amazon.com/vpc/latest/userguide/working-with-vpcs.html#AddaSubnet)\.


## Creating index snapshots

- **Note**  
Repository names cannot start with "cs\-"\. Additionally, you shouldn't write to the same repository from multiple domains\. Only one domain should have write access to the repository\.
- **Tip**  
A Java\-based code sample is available in [Signing HTTP Requests](request-signing.md#request-signing-java)\.
- **Note**  
The time required to take a snapshot increases with the size of the OpenSearch Service domain\. Long\-running snapshot operations sometimes encounter the following error: `504 GATEWAY_TIMEOUT`\. You can typically ignore these errors and wait for the operation to complete successfully\. Run the following command to verify the state of all snapshots of your domain:
- **Note**  
Most automated snapshots are stored in the `cs-automated` repository\. If your domain encrypts data at rest, they're stored in the `cs-automated-enc` repository\. If you don't see the manual snapshot repository you're looking for, make sure you [registered it](#managedomains-snapshot-registerdirectory) to the domain\.
- **Note**  
If not all primary shards were available for the indexes involved, a snapshot might have a `state` of `PARTIAL`\. This value indicates that data from at least one shard wasn't stored successfully\. You can still restore from a partial snapshot, but you might need to use older snapshots to restore any missing indexes\.


## Upgrading domains

- **Note**  
OpenSearch and Elasticsearch version upgrades differ from service software updates\. For information on updating the service software for your OpenSearch Service domain, see [Service software updates in Amazon OpenSearch Service](service-software.md)\.


## Tagging domains

- **Note**  
Tags are cached for authorization purposes\. Because of this, additions and updates to tags on OpenSearch Service domains might take several minutes before they're available\.

