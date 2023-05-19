---
id: Working with Direct Connect gateways
title: Working with Direct Connect gateways
created: 1683841041000
updated: 1683841041000
---
# Working with Direct Connect gateways

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-direct-connect-user-guide.git)
{% endhint %}

## Virtual private gateway associations

- **Note**  
If you are planning to use the virtual private gateway for a Direct Connect gateway and a dynamic VPN connection, set the ASN on the virtual private gateway to the value that you require for the VPN connection\. Otherwise, the ASN on the virtual private gateway can be set to any permitted value\. The Direct Connect gateway advertises all connected VPCs over the ASN assigned to it\.
- **Note**  
If you're accepting a hosted private virtual interface, you can associate it with a Direct Connect gateway in your account\. For more information, see [Accept a hosted virtual interface](accepthostedvirtualinterface.md)\.


## Transit gateway associations

- **Important**  
If you associate your transit gateway with one or more Direct Connect gateways, the Autonomous System Number \(ASN\) used by the transit gateway and the Direct Connect gateway must be different\. For example, if you use the default ASN 64512 for both the transit gateway and the Direct Connect gateway, the association request fails\.


## Allowed prefixes interactions

- **Note**  
The allowed list only functions as a filter, and only the associated VPC CIDR will be advertised to the customer gateway\.

