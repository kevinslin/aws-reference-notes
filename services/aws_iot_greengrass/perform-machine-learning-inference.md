---
id: Perform machine learning inference
title: Perform machine learning inference
created: 1683841041000
updated: 1683841041000
---
# Perform machine learning inference

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Use Lookout for Vision

- **Note**  
AWS IoT Greengrass doesn't currently support this feature on Windows core devices\.


## Customize your machine learning components

- **Note**  
This step creates the component in the AWS IoT Greengrass service in the AWS Cloud\. You can use the Greengrass CLI to develop, test, and deploy your component locally before you upload it to the cloud\. For more information, see [Develop AWS IoT Greengrass components](develop-greengrass-components.md)\.
- **Note**  <a name="s3-artifacts-note"></a>
<a name="sr-artifacts-req"></a>You must store your artifacts in S3 buckets that are in the same AWS account and AWS Region as the components\. To enable AWS IoT Greengrass to access these artifacts, the [Greengrass device role](device-service-role.md) must allow the `s3:GetObject` action\. For more information about the device role, see [Authorize core devices to interact with AWS services](device-service-role.md)\.
- **Note**  <a name="s3-artifacts-note"></a>
<a name="sr-artifacts-req"></a>You must store your artifacts in S3 buckets that are in the same AWS account and AWS Region as the components\. To enable AWS IoT Greengrass to access these artifacts, the [Greengrass device role](device-service-role.md) must allow the `s3:GetObject` action\. For more information about the device role, see [Authorize core devices to interact with AWS services](device-service-role.md)\.
- **Note**  
This step creates the component in the AWS IoT Greengrass service in the AWS Cloud\. You can use the Greengrass CLI to develop, test, and deploy your component locally before you upload it to the cloud\. For more information, see [Develop AWS IoT Greengrass components](develop-greengrass-components.md)\.


## Troubleshooting

- **Note**  
For the DLR component v1\.3\.x, you set the `MLRootPath` parameter in the configuration of the inference component, and the default value is `$HOME/greengrass_ml`\.

