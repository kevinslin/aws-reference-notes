---
id: Interact with local IoT devices
title: Interact with local IoT devices
created: 1683841041000
updated: 1683841041000
---
# Interact with local IoT devices

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Client device components

- **Note**  <a name="component-nucleus-dependency-update-note"></a>
Several AWS\-provided components depend on specific minor versions of the Greengrass nucleus\. Because of this dependency, you need to update these components when you update the Greengrass nucleus to a new minor version\. For information about the specific versions of the nucleus that each component depends on, see the corresponding component topic\. For more information about updating the nucleus, see [Update the AWS IoT Greengrass Core software \(OTA\)](update-greengrass-core-v2.md)\.


## Connect client devices to core devices

- **Important**  <a name="client-device-support-nucleus-requirement"></a>
The core device must run [Greengrass nucleus](greengrass-nucleus-component.md) v2\.2\.0 or later to support client devices\.
- **Note**  <a name="note-deploy-one-mqtt-broker"></a>
We recommend that you deploy only one MQTT broker component\. The [MQTT bridge](mqtt-bridge-component.md) and [IP detector](ip-detector-component.md) components work with only one MQTT broker component at a time\. If you deploy multiple MQTT broker components, you must configure them to use different ports\.


## Relay MQTT messages between client devices and AWS IoT Core

- **Note**  <a name="mqtt-bridge-component-iotcore-qos-1-note"></a>
The MQTT bridge uses QoS 1 to publish and subscribe to AWS IoT Core, even when a client device uses QoS 0 to publish and subscribe to the local MQTT broker\. As a result, you might observe additional latency when you relay MQTT messages from client devices on the local MQTT broker to AWS IoT Core\. For more information about MQTT configuration on core devices, see [Configure MQTT timeouts and cache settings](configure-greengrass-core-v2.md#configure-mqtt)\.


## Interact with and sync client device shadows

- **Note**  
The shadow manager component doesn't sync shadows with AWS IoT Core by default\. You must configure the shadow manager component to specify which client device shadows to sync\.
- **Note**  
You can use these configuration examples in the AWS IoT Greengrass console\. If you use the AWS IoT Greengrass API, the `merge` configuration update requires a serialized JSON object, so you must serialize the following JSON objects into strings\. For more information, see [Update component configurations](update-component-configurations.md)\.

