---
id: Networking
title: Networking
created: 1683841041000
updated: 1683841041000
---
# Networking

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-app-runner-developer-guide.git)
{% endhint %}

## Outgoing traffic

- **Note**  
The following traffic isn't affected when you associate your service with a VPC:  
**Inbound traffic** – Incoming messages that your application receives are unaffected by an associated VPC\. The messages are routed through the public domain name that's associated with your service and don't interact with the VPC\.
**App Runner traffic** – App Runner manages several actions on your behalf, such as pulling source code and images, pushing logs, and retrieving secrets\. The traffic that these actions generate isn't routed through your VPC\.
- **Note**  
A few Availability Zones in some AWS Regions don't support subnets that can be used with App Runner services\. If you choose subnets in these Availability Zones, your service fails to be created or updated\. For these situations, App Runner provides a detailed error message pointing to the unsupported subnets and Availability Zones\. Remove the unsupported subnets from your request and try again\.

