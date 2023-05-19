---
id: Setting up Greengrass core devices
title: Setting up Greengrass core devices
created: 1683841041000
updated: 1683841041000
---
# Setting up Greengrass core devices

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Install the AWS IoT Greengrass Core software

- **Important**  
Before you download and install the AWS IoT Greengrass Core software, check that your core device meets the [requirements](setting-up.md#greengrass-v2-requirements) to install and run the AWS IoT Greengrass Core software v2\.0\.


## Run the AWS IoT Greengrass Core software

- **Important**  <a name="windows-system-service-requirement-important-note"></a>
On Windows core devices, you must set up the AWS IoT Greengrass Core software as a system service\.


## Configure the AWS IoT Greengrass Core software

- **Important**  <a name="windows-system-service-requirement-important-note"></a>
On Windows core devices, you must set up the AWS IoT Greengrass Core software as a system service\.
- **Note**  <a name="windows-ignore-shutdown-signal-behavior-note"></a>
On Windows devices, the AWS IoT Greengrass Core software ignores this shutdown signal while it shuts down Greengrass component processes\. If the AWS IoT Greengrass Core software ignores the shutdown signal when you run this command, wait a few seconds, and try again\.
- **Note**  <a name="windows-ignore-shutdown-signal-behavior-note"></a>
On Windows devices, the AWS IoT Greengrass Core software ignores this shutdown signal while it shuts down Greengrass component processes\. If the AWS IoT Greengrass Core software ignores the shutdown signal when you run this command, wait a few seconds, and try again\.
- **Note**  
On Windows\-based devices, you must specify at least a default user to run components\.  
On Linux\-based devices, the following considerations apply if you don't configure a user to run components:   
If you run the AWS IoT Greengrass Core software as root, then the software won't run components\. You must specify a default user to run components if you run as root\.
If you run the AWS IoT Greengrass Core software as a non\-root user, then the software runs components as that user\.
- **Note**  
On Windows\-based devices, the LocalSystem account runs the Greengrass nucleus, and you must use the PsExec utility to store the component user information in the LocalSystem account\. Using the Credential Manager application stores this information in the Windows account of the currently logged on user, instead of the LocalSystem account\.
- **Note**  
You can also set the default user when you install the AWS IoT Greengrass Core software with the `--component-default-user` option\. For more information, see [Install the AWS IoT Greengrass Core software](install-greengrass-core-v2.md)\.
- **Note**  
The user that you specify must exist, and the user name and password for this user must be stored in the credential manager instance of the LocalSystem account on your Windows device\. For more information, see [Set up a component user on Windows devices](#create-component-user-windows)\.
- **Note**  
This feature is available for v2\.4\.0 and later of the [Greengrass nucleus component](greengrass-nucleus-component.md)\. AWS IoT Greengrass doesn't currently support this feature on Windows core devices\.
- **Important**  
System resource limits aren't supported when you [run AWS IoT Greengrass Core software in a Docker container](run-greengrass-docker.md)\.
- **Note**  
Greengrass core devices that run [Greengrass nucleus component](greengrass-nucleus-component.md) v2\.0\.3 and earlier use port 8443 to connect to the AWS IoT Greengrass data plane endpoint\. These devices must be able to connect to this endpoint on port 8443\. For more information, see [Allow device traffic through a proxy or firewall](allow-device-traffic.md)\.
- **Important**  
If your core device runs a version of the [Greengrass nucleus](greengrass-nucleus-component.md) earlier than v2\.4\.0, your device's role must allow the following permissions to use a network proxy:  
`iot:Connect`
`iot:Publish`
`iot:Receive`
`iot:Subscribe`
This is necessary because the device uses AWS credentials from the token exchange service to authenticate MQTT connections to AWS IoT\. The device uses MQTT to receive and install deployments from the AWS Cloud, so your device won't work unless you define these permissions on its role\. Devices typically use X\.509 certificates to authenticate MQTT connections, but devices can't do this to authenticate when they use a proxy\.  
For more information about how to configure the device role, see [Authorize core devices to interact with AWS services](device-service-role.md)\.


## Uninstall the AWS IoT Greengrass Core software

- **Note**  
You must run Command Prompt as an administrator to run these commands\.
- **Note**  
You must run PowerShell as an administrator to run these commands\.

