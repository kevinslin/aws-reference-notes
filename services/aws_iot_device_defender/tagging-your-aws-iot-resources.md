---
id: Tagging your AWS IoT resources
title: Tagging your AWS IoT resources
created: 1683841041000
updated: 1683841041000
---
# Tagging your AWS IoT resources

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Using tags with IAM policies

- **Note**  
The condition context keys and values in an IAM policy apply only to those AWS IoT actions where an identifier for a resource capable of being tagged is a required parameter\. For example, the use of [DescribeEndpoint](https://docs.aws.amazon.com/iot/latest/apireference/API_DescribeEndpoint) is not allowed or denied on the basis of condition context keys and values because no taggable resource \(thing groups, thing types, topic rules, jobs, or security profile\) is referenced in this request\. For more information about AWS IoT resources that are taggable and condition keys they support, read [Actions, resources, and condition keys for AWS IoT](https://docs.aws.amazon.com/service-authorization/latest/reference/list_awsiot.html)\.
- **Note**  
If you allow or deny users access to resources based on tags, you must consider explicitly denying users the ability to add those tags to or remove them from the same resources\. Otherwise, it's possible for a user to circumvent your restrictions and gain access to a resource by modifying its tags\.


## Billing groups

- **Note**  
To accurately associate usage and cost data with those things you have placed in billing groups, each device or application must:  
Be registered as a thing in AWS IoT\. For more information, see [Managing devices with AWS IoT](iot-thing-management.md)\.
Connect to the AWS IoT message broker through MQTT using only the thing's name as the client ID\. For more information, see [Device communication protocols](protocols.md)\.
Authenticate using a client certificate associated with the thing\.

