---
id: Virtual interfaces
title: Virtual interfaces
created: 1683841041000
updated: 1683841041000
---
# Virtual interfaces

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-direct-connect-user-guide.git)
{% endhint %}

## Create a virtual interface

- **Important**  
If you associate your transit gateway with one or more Direct Connect gateways, the Autonomous System Number \(ASN\) used by the transit gateway and the Direct Connect gateway must be different\. For example, if you use the default ASN 64512 for both the transit gateway and the Direct Connect gateway, the association request fails\.


## Set network MTU for private virtual interfaces or transit virtual interfaces

- **Important**  
Jumbo frames will apply only to propagated routes via AWS Direct Connect and static routes via transit gateways\. Jumbo frames on transit gateways support only 8500 bytes\.  
If an EC2 instance doesn't support jumbo frames, it drops jumbo frames from AWS Direct Connect\. All EC2 instance types support jumbo frames except for C1, CC1, T1, and M1\. For more information, see [Network Maximum Transmission Unit \(MTU\) for Your EC2 Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/network_mtu.html) in the *Amazon EC2 User Guide for Linux Instances*\.


## Migrate a virtual interface

- **Note**  
You can migrate a virtual interface to a new connection within the same Region, but you can't migrate it from one Region to another\. When you migrate or associate an existing virtual interface to a new connection, the configuration parameters associated with those virtual interfaces are the same\. To work around this, you can pre\-stage the configuration on the connection, and then update the BGP configuration\. 
You can't migrate a VIF from one hosted connection to another hosted connection\. VLAN IDs are unique; therefore, migrating a VIF in this way would mean the VLANs don't match\. You either need to delete the connection or VIF, and then recreate that using a VLAN that's the same for both the connection and the VIF\.
- **Important**  
The virtual interface will go down for a brief period\. We recommend you perform this procedure during a maintenance window\.

