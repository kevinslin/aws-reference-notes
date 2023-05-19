---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Develop a component that defers component updates

- **Note**  
A *component* is a software module that runs on AWS IoT Greengrass core devices\. Components enable you to create and manage complex applications as discrete building blocks that you can reuse from one Greengrass core device to another\.
- **Note**  
The AWS IoT Greengrass Core software doesn't send update notifications for local deployments, so you deploy this component using the AWS IoT Greengrass cloud service to test it\.
- **Note**  
If the file doesn't exist, the deployment may not be complete yet\. If the file doesn't exist within 30 seconds, the deployment likely failed\. This can occur if the core device doesn't have permission to download the component's artifacts from the S3 bucket, for example\. Run the following command to view the AWS IoT Greengrass Core software log file\. This file includes logs from the Greengrass core device's deployment service\.


## Interact with local IoT devices over MQTT

- **Note**  
The AWS IoT Device SDK is also available in other programming languages\. This tutorial uses the AWS IoT Device SDK v2 for Python, but you can explore the other SDKs for your use case\. For more information, see [AWS IoT Device SDKs](https://docs.aws.amazon.com/iot/latest/developerguide/iot-sdks.html) in the *AWS IoT Core Developer Guide*\.
- **Important**  <a name="local-artifact-folder-name-requirements"></a>
You must use the following format for the artifact folder path\. Include the component name and version that you specify in the recipe\.
- **Note**  
This component uses the IPC client V2 in the [AWS IoT Device SDK v2 for Python](https://github.com/aws/aws-iot-device-sdk-python-v2) to communicate with the AWS IoT Greengrass Core software\. Compared to the original IPC client, the IPC client V2 reduces the amount of code that you need to write to use IPC in custom components\.
- **Important**  <a name="local-artifact-folder-name-requirements"></a>
You must use the following format for the artifact folder path\. Include the component name and version that you specify in the recipe\.
- **Note**  
The client device's shadow is in sync between the core device and the client device\. However, the core device doesn't sync the client device's shadow with AWS IoT Core\. You might sync a shadow with AWS IoT Core to view or modify the state of all devices in your fleet, for example\. For more information about how to configure the shadow manager component to sync shadows with AWS IoT Core, see [Sync local device shadows with AWS IoT Core](sync-shadows-with-iot-core.md)\.


## Perform sample image classification inference on images from a camera

- **Note**  
This tutorial accesses the camera module for [Raspberry Pi](https://www.raspberrypi.org/) or [NVIDIA Jetson Nano](https://developer.nvidia.com/embedded/jetson-nano) devices, but AWS IoT Greengrass supports other devices on Armv7l, Armv8, or x86\_64 platforms\. To set up a camera for a different device, consult the relevant documentation for your device\.
- **Note**  
For Armv8 \(AArch64\) devices, such as a Jetson Nano, you don't need to create a symlink to enable the inference component to access the camera from the virtual environment that is created by the runtime component\.

