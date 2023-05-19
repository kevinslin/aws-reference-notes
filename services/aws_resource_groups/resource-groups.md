---
id: Resource groups
title: Resource groups
created: 1683841041000
updated: 1683841041000
---
# Resource groups

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-resource-groups-user-guide.git)
{% endhint %}

## Updating groups

- **Note**  
You can update only resource groups that you own\. The **Owner** column shows account ownership for each resource group\. Any groups with an account owner other than the one you're signed in to were created in AWS License Manager\. For more information, see [Host resource groups in AWS License Manager](https://docs.aws.amazon.com/license-manager/latest/userguide/host-resource-groups.html) in the *License Manager User Guide*\.


## Monitoring resource groups for changes

- **Important**  
To successfully receive and respond to group events, you must make changes to both Resource Groups and EventBridge\. You can perform the changes in any order, but no group events are published to EventBridge targets until after you make changes to both services\.
The resource group changes don't include changes to any tags attached to the resource group itself\. To generate events based on tag changes to your groups, you must use an EventBridge rule that uses the `aws.tag` source, instead of the `aws.resource-groups` source\. For more information, see [Tag change events on AWS Resources](https://docs.aws.amazon.com/eventbridge/latest/userguide/event-types.html#tag-event-types) in the *Amazon EventBridge User Guide*\.


## Service configurations

- **Note**  
Because resource groups of this type are automatically created and maintained by AWS and not managed by the user, these resource groups do not count against your quota limit for the [maximum number of resource groups that you can create in your AWS account](https://console.aws.amazon.com/servicequotas/home/services/resource-groups/quotas)\.
- **Note**  
To change any of these elements, you must modify the application using the AppRegistry console or that service's AWS SDK and AWS CLI operations\.
- **Note**  
Because resource groups of this type are automatically created and maintained by AWS and not managed by the user, these resource groups do not count against your quota limit for the [maximum number of resource groups that you can create in your AWS account](https://console.aws.amazon.com/servicequotas/home/services/resource-groups/quotas)\.
- **Note**  
To change any of these elements, you must modify the application using the AppRegistry console or equivalent AWS SDK and AWS CLI operations\.

