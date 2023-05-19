---
id: Manage core devices with AWS Systems Manager
title: Manage core devices with AWS Systems Manager
created: 1683841041000
updated: 1683841041000
---
# Manage core devices with AWS Systems Manager

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Install the Systems Manager Agent

- **Note**  <a name="deploy-ssm-agent-component-configuration-options"></a>
If the core device already runs the Systems Manager Agent registered with a hybrid activation, change `SSMOverrideExistingRegistration` to `true`\. This parameter specifies whether the Systems Manager Agent component registers the core device when the Systems Manager Agent is already running on the device with a hybrid activation\.  
You can also specify tags \(`SSMResourceTags`\) to add to the Systems Manager managed node that the Systems Manager Agent component creates for the core device\. For more information, see [Systems Manager Agent component configuration](systems-manager-agent-component.md#systems-manager-agent-component-configuration)\.
- **Note**  <a name="deploy-ssm-agent-component-configuration-options"></a>
If the core device already runs the Systems Manager Agent registered with a hybrid activation, change `SSMOverrideExistingRegistration` to `true`\. This parameter specifies whether the Systems Manager Agent component registers the core device when the Systems Manager Agent is already running on the device with a hybrid activation\.  
You can also specify tags \(`SSMResourceTags`\) to add to the Systems Manager managed node that the Systems Manager Agent component creates for the core device\. For more information, see [Systems Manager Agent component configuration](systems-manager-agent-component.md#systems-manager-agent-component-configuration)\.

