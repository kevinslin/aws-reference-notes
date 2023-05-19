---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Device authentication and authorization

- **Important**  
<a name="thing-policy-variable-not-supported"></a>[Thing policy variables](https://docs.aws.amazon.com/iot/latest/developerguide/thing-policy-variables.html) \(`iot:Connection.Thing.*`\) aren't supported for in AWS IoT policies for core devices or Greengrass data plane operations\. Instead, you can use a wildcard that matches multiple devices that have similar names\. For example, you can specify `MyGreengrassDevice*` to match `MyGreengrassDevice1`, `MyGreengrassDevice2`, and so on\.
- **Note**  
AWS IoT Core enables you to attach AWS IoT policies to thing groups to define permissions for groups of devices\. Thing group policies don't allow access to AWS IoT Greengrass data plane operations\. To allow a thing access to an AWS IoT Greengrass data plane operation, add the permission to an AWS IoT policy that you attach to the thing's certificate\.
- **Note**  
If you used the [AWS IoT Greengrass Core software installer to provision resources](quick-installation.md), your core device has an AWS IoT policy that allows access to all AWS IoT Greengrass actions \(`greengrass:*`\)\. You can follow these steps to restrict access to only the actions that a core device uses\.
- **Important**  
Later versions of the [Greengrass nucleus component](greengrass-nucleus-component.md) require additional permissions on the minimal AWS IoT policy\. You might need to [update your core devices' AWS IoT policies](#update-core-device-iot-policy) to grant additional permissions\.  
Core devices that run Greengrass nucleus v2\.5\.0 and later use the `greengrass:ListThingGroupsForCoreDevice` permission to uninstall components when you remove a core device from a thing group\.
Core devices that run Greengrass nucleus v2\.3\.0 and later use the `greengrass:GetDeploymentConfiguration` permission to support large deployment configuration documents\.


## Identity and access management

- **Note**  
This topic describes IAM concepts and features\. For information about IAM features supported by AWS IoT Greengrass, see [How AWS IoT Greengrass works with IAM](security_iam_service-with-iam.md)\.


## Code integrity

- **Note**  
Amazon S3 provides a feature called S3 Object Lock that you can use to protect against changes to component artifacts in S3 buckets your AWS account\. You can use S3 Object Lock to prevent component artifacts from being deleted or overwritten\. For more information, see [Using S3 Object Lock](https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html) in the *Amazon Simple Storage Service User Guide*\.


## VPC endpoints (AWS PrivateLink)

- **Note**  
Currently, you can't configure Greengrass core devices to operate completely within your VPC\.

