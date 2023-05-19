---
id: X-Ray daemon
title: X-Ray daemon
created: 1683841041000
updated: 1683841041000
---
# X-Ray daemon

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-xray-developer-guide.git)
{% endhint %}

## On Elastic Beanstalk

- **Note**  
The daemon uses your environment's instance profile for permissions\. For instructions about adding permissions to the Elastic Beanstalk instance profile, see [Giving the daemon permission to send data to X\-Ray](xray-daemon.md#xray-daemon-permissions)\.


## On Amazon ECS

- **Note**  
Flags `-t` and `-b` are required to specify a binding address to listen to the loopback of a multi\-container environment\.

