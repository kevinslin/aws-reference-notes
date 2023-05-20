---
id: Networking
title: Networking
created: 1683841041000
updated: 1683841041000
---
# Networking

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ec2-user-guide.git)
{% endhint %}

## Regions and Zones

- **Considerations**  
Some AWS resources might not be available in all Regions\. Ensure that you can create the resources that you need in the desired Regions before you launch an instance\.
- **Considerations**


## Instance IP addressing

- **Note**  
You can create a VPC with a publicly routable CIDR block that falls outside of the private IPv4 address ranges specified in RFC 1918\. However, for the purposes of this documentation, we refer to private IPv4 addresses \(or 'private IP addresses'\) as the IP addresses that are within the IPv4 CIDR range of your VPC\.
- **Note**  
Instances that access other instances through their public NAT IP address are charged for regional or Internet data transfer, depending on whether the instances are in the same Region\.
- **Considerations**


## Instance hostname types

- **Note**  
Changing the subnet settings doesn't change the configuration of EC2 instances that are already launched in the subnet\.
- **Important**  
To change the **Use resource based naming as guest OS hostname** setting, you must first stop the instance\. To change the **Answer DNS hostname IPv4 \(A record\) request** or **Answer DNS hostname IPv6 \(AAAA record\) requests** settings, you don't have to stop the instance\.
To modify any of the settings for non\-EBS backed EC2 instance types, you cannot stop the instance\. You must terminate the instance and launch a new instance with the desired Hostname type and DNS Hostname configurations\.


## Bring your own IP addresses

- **Note**  
The following steps describe how to bring your own IP address range for use in Amazon EC2 only\. For steps to bring your own IP address range for use in AWS Global Accelerator, see [Bring your own IP addresses \(BYOIP\)](https://docs.aws.amazon.com/global-accelerator/latest/dg/using-byoip.html) in the *AWS Global Accelerator Developer Guide*\.
- **Note**  
A ROA is not required for non\-publicly advertised IPv6 address space\.
- **Note**  
The Common Name is not needed for AWS provisioning\. It can be any internal or public domain name\.
- **Important**  
If you are creating a ROA object for Amazon VPC IP Address Manager \(IPAM\), when you create the ROAs, for IPv4 CIDRs you must set the maximum length of an IP address prefix to `/24`\. For IPv6 CIDRs, if you are adding them to an advertisable pool, the maximum length of an IP address prefix must be `/48`\. This ensures that you have full flexibility to divide your public IP address across AWS Regions\. IPAM enforces the maximum length you set\. For more information about BYOIP addresses to IPAM, see [Tutorial: BYOIP address CIDRs to IPAM](https://docs.aws.amazon.com/vpc/latest/ipam/tutorials-byoip-ipam.html) in the *Amazon VPC IPAM User Guide*\.
- **Note**  
This step is not required for non\-publicly advertised IPv6 address space\.
- **Important**  
You can only specify whether an address range is publicly advertised during provisioning\. You cannot change the advertisable status later on\.


## Elastic IP addresses

- **Note**  
If you contacted AWS support to set up reverse DNS for an Elastic IP \(EIP\) address, you can remove the reverse DNS, but you can’t release the Elastic IP address because it’s been locked by AWS support\. To unlock the Elastic IP address, contact [AWS Support](https://console.aws.amazon.com/support/home#/)\. Once the Elastic IP address is unlocked, you can release the Elastic IP address\.
- **Considerations**
- **Note**  
If you receive the following error when you run the command, you can submit a [Request to remove email sending limitations](http://aws.amazon.com/forms/ec2-email-limit-rdns-request) to customer support for assistance\.  
*The address with allocation id cannot be released because it is locked to your account*\.


## Network interfaces

- **Important**  
For EC2 instances in an IPv6\-only subnet, if you attach a secondary network interface to the instance, the private DNS hostname of the second network interface will resolve to the first IPv6 address on the instance's first network interface\. For more information about EC2 instance private DNS hostnames, see [Amazon EC2 instance hostname types](ec2-instance-naming.md)\.


## Elastic Fabric Adapter

- **Note**  
The OS\-bypass capabilities of EFAs are not supported on Windows instances\. If you attach an EFA to a Windows instance, the instance functions as an Elastic Network Adapter, without the added EFA capabilities\.
- **Note**  
Libfabric is a core component of the OpenFabrics Interfaces \(OFI\) framework, which defines and exports the user\-space API of OFI\. For more information, see the [Libfabric OpenFabrics](https://ofiwg.github.io/libfabric/) website\.
- **Note**  
Ubuntu 20\.04 supports peer direct support when used with `dl1.24xlarge` instances\.


## Placement groups

- **Note**  
You can tag a placement group on creation using the command line tools only\.


## Network MTU

- **Important**  
Path MTU Discovery does not guarantee that jumbo frames will not be dropped by some routers\. An internet gateway in your VPC will forward packets up to 1500 bytes only\. 1500 MTU packets are recommended for internet traffic\.

