---
id: "What is Route\_53 Resolver?"
title: "What is Route\_53 Resolver?"
created: 1683841041000
updated: 1683841041000
---
# What is Route 53 Resolver?

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-route53-docs.git)
{% endhint %}

## Resolving DNS queries between VPCs and your network

- **Note**  
 Forwarding private DNS queries to any VPC CIDR \+ 2 address from your on\-premises DNS servers is not supported, and can cause unstable results\. Instead, we recommend that you use a Resolver inbound endpoint\.
- **Note**  
When you create a Resolver endpoint, you can't specify a VPC that has the instance tenancy attribute set to `dedicated`\. For more information, see [Using Resolver in VPCs that are configured for dedicated instance tenancy](#resolver-considerations-dedicated-instance-tenancy)\.
- **Note**  
If you create a conditional forwarding rule for "\." \(dot\) or "com", we recommend that you also create a system rule for amazonaws\.com\. \(System rules cause Resolver to locally resolve DNS queries for specific domains and subdomains\.\) Creating this system rule improves performance, reduces the number of queries that are forwarded to your network, and reduces Resolver charges\.


## Forwarding outbound DNS queries to your network

- **Important**  
After you create an outbound endpoint, you must create one or more rules and associate them with one or more VPCs\. Rules specify the domain names of the DNS queries that you want to forward to your network\.<a name="resolver-forwarding-outbound-queries-configuring-create-endpoint-procedure"></a>


## Managing inbound endpoints

- **Important**  
If you delete an inbound endpoint, DNS queries from your network are no longer forwarded to Resolver in the VPC that you specified in the endpoint\. <a name="resolver-forwarding-inbound-queries-managing-deleting-procedure"></a>


## Managing outbound endpoints

- **Important**  
If you delete an outbound endpoint, Resolver stops forwarding DNS queries from your VPC to your network for rules that specify the deleted outbound endpoint\.<a name="resolver-forwarding-outbound-queries-managing-deleting-procedure"></a>


## Enabling DNSSEC validation

- **Important**  
Enabling DNSSEC validation can impact DNS resolution for public DNS records from AWS resources in a VPC, which could result in an outage\. Be aware that enabling or disabling DNSSEC validation can take several minutes\.
- **Note**  
At this time, the Amazon Route 53 Resolver in your VPC \(aka AmazonProvidedDNS\) ignores the DO \(DNSSEC OK\) EDNS header bit and the CD \(Checking Disabled\) bit in the DNS query\. If you have configured DNSSEC, this means that while the Route 53 Resolver does perform DNSSEC validation, it doesn't return DNSSEC records nor set the AD bit in the response\. Therefore, performing your own DNSSEC validation is not currently supported by the Route 53 Resolver\. If you need to do this you will have to perform your own recursive DNS resolution\.<a name="resolver-dnssec-validation-procedure"></a>

