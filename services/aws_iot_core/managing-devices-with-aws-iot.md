---
id: Managing devices with AWS IoT
title: Managing devices with AWS IoT
created: 1683841041000
updated: 1683841041000
---
# Managing devices with AWS IoT

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## How to manage things with the registry

- **Note**  
We don't recommend using personally identifiable information in your thing names\.


## Thing types

- **Note**  
You must wait five minutes after you deprecate a thing type before you can delete it\.


## Static thing groups

- **Note**  
We don't recommend using personally identifiable information in your thing group names\.
- **Important**  
Keep in mind the following limits when creating thing group hierarchies:  
A thing group can have only one direct parent\.
The number of direct child groups a thing group can have is [limited](https://docs.aws.amazon.com/general/latest/gr/iot_device_management.html#thing-group-limits)\.
The maximum depth of a group hierarchy is [limited](https://docs.aws.amazon.com/general/latest/gr/iot_device_management.html#thing-group-limits)\.
The number of attributes a thing group can have is [limited](https://docs.aws.amazon.com/general/latest/gr/iot_device_management.html#thing-group-limits)\. \(Attributes are name\-value pairs you can use to store information about a group\.\) The lengths of each attribute name and each value are also [limited](https://docs.aws.amazon.com/general/latest/gr/iot_device_management.html#thing-group-limits)\.
- **Important**  
You can add a thing to a maximum of 10 groups\. But you can't add a thing to more than one group in the same hierarchy\. \(In other words, you can't add a thing to two groups which share a common parent\.\)  
If a thing belongs to as many thing groups as possible, and one or more of those groups is a dynamic thing group, you can use the [https://docs.aws.amazon.com/iot/latest/apireference/API_AddThingToThingGroup.html#iot-AddThingToThingGroup-request-overrideDynamicGroups](https://docs.aws.amazon.com/iot/latest/apireference/API_AddThingToThingGroup.html#iot-AddThingToThingGroup-request-overrideDynamicGroups) flag to make static groups take priority over dynamic groups\.
- **Note**  
This operation is [eventually consistent](https://web.stanford.edu/class/cs345d-01/rl/eventually-consistent.pdf)\. In other words, changes to the thing group might not be reflected immediately\.
- **Note**  
This operation is [eventually consistent](https://web.stanford.edu/class/cs345d-01/rl/eventually-consistent.pdf)\. In other words, changes to the thing group might not be reflected immediately\.
- **Note**  
The number of attributes that a thing can have is [limited](https://docs.aws.amazon.com/general/latest/gr/iot_device_management.html#thing-limits)\.
- **Important**  
If you try to delete a thing group that has child thing groups, you receive an error:
- **Important**  
You can attach a maximum number of two policies to a group\.
- **Note**  
We don't recommend using personally identifiable information in your policy names\.


## Dynamic thing groups

- **Note**  
We don't recommend using personally identifiable information in your dynamic thing group names\.
- **Note**  
After you create a dynamic thing group, you can use the group, regardless of its status\. Only dynamic thing groups with an `ACTIVE` status include all of the things that match the search query for that dynamic thing group\. Dynamic thing groups with `BUILDING` and `REBUILDING` statuses might not include all of the things that match the search query\.
- **Note**  
If you have permissions to query the fleet index, you can access the data of things across the entire fleet\.

