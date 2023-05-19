---
id: Components
title: Components
created: 1683841041000
updated: 1683841041000
---
# Components

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## AWS-provided components

- **Note**  <a name="component-nucleus-dependency-update-note"></a>
Several AWS\-provided components depend on specific minor versions of the Greengrass nucleus\. Because of this dependency, you need to update these components when you update the Greengrass nucleus to a new minor version\. For information about the specific versions of the nucleus that each component depends on, see the corresponding component topic\. For more information about updating the nucleus, see [Update the AWS IoT Greengrass Core software \(OTA\)](update-greengrass-core-v2.md)\.


## Develop components

- **Note**  <a name="semver-note"></a>
<a name="semver-para"></a>AWS IoT Greengrass uses semantic versions for components\. Semantic versions follow a *major*\.*minor*\.*patch* number system\. For example, version `1.0.0` represents the first major release for a component\. For more information, see the [semantic version specification](https://semver.org/)\.
- **Note**  <a name="recipe-component-type-recommendation"></a>
We don't recommend that you specify the component type in a recipe\. AWS IoT Greengrass sets the type for you when you create a component\.


## Deploy components to devices

- **Note**  <a name="thing-group-removal-behavior"></a>
When you remove a core device from a thing group, the component deployment behavior depends on the version of the [Greengrass nucleus](greengrass-nucleus-component.md) that the core device runs\.  
The thing group removal behavior depends on whether the core device's AWS IoT policy grants the `greengrass:ListThingGroupsForCoreDevice` permission\. For more information about this permission and AWS IoT policies for core devices, see [Device authentication and authorization for AWS IoT Greengrass](device-auth.md)\.  
**If the AWS IoT policy grants this permission**  
<a name="thing-group-removal-behavior-remove-components"></a>When you remove a core device from a thing group, AWS IoT Greengrass removes that thing group's components from the device in the next deployment\. However, if another deployment targets the core device and includes a component, the core device doesn't remove that component\.
**If the AWS IoT policy doesn't grant this permission**  
<a name="thing-group-removal-behavior-no-remove-components"></a>When you remove a core device from a thing group, AWS IoT Greengrass doesn't delete that thing group's components from the device\. Because of this, we recommend that you don't remove core devices from thing groups where you deploy components\.  
<a name="thing-group-removal-behavior-no-remove-components-how-to-remove"></a>To remove a component from a device, where the device is no longer a member of the thing group that deploys that component, use the [deployment create](gg-cli-deployment.md#deployment-create) command of the Greengrass CLI\. Specify the component to remove with the `--remove` argument, and specify the thing group with the `--groupId` argument\.
<a name="thing-group-removal-behavior-remove-components"></a>When you remove a core device from a thing group, AWS IoT Greengrass removes that thing group's components from the device in the next deployment\. However, if another deployment targets the core device and includes a component, the core device doesn't remove that component\.  
This behavior requires that the core device's AWS IoT policy grants the `greengrass:ListThingGroupsForCoreDevice` permission\. If a core device doesn't have this permission, the core device fails to apply deployments\. For more information, see [Device authentication and authorization for AWS IoT Greengrass](device-auth.md)\.
<a name="thing-group-removal-behavior-no-remove-components"></a>When you remove a core device from a thing group, AWS IoT Greengrass doesn't delete that thing group's components from the device\. Because of this, we recommend that you don't remove core devices from thing groups where you deploy components\.  
<a name="thing-group-removal-behavior-no-remove-components-how-to-remove"></a>To remove a component from a device, where the device is no longer a member of the thing group that deploys that component, use the [deployment create](gg-cli-deployment.md#deployment-create) command of the Greengrass CLI\. Specify the component to remove with the `--remove` argument, and specify the thing group with the `--groupId` argument\.
- **Important**  
Custom components can define artifacts in S3 buckets\. When the AWS IoT Greengrass Core software deploys a component, it downloads the component's artifacts from the AWS Cloud\. Core device roles don't allow access to S3 buckets by default\. To deploy custom components that define artifacts in an S3 bucket, the core device role must grant permissions to download artifacts from that bucket\. For more information, see [Allow access to S3 buckets for component artifacts](device-service-role.md#device-service-role-access-s3-bucket)\.

