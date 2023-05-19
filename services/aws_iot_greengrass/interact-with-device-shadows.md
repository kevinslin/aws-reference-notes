---
id: Interact with device shadows
title: Interact with device shadows
created: 1683841041000
updated: 1683841041000
---
# Interact with device shadows

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Interact with shadows in components

- **Note**  
By default, deploying the shadow manager component enables local shadow operations only\. To enable AWS IoT Greengrass to sync shadow state information for core device shadows or any shadows for client devices to the corresponding cloud shadow documents in AWS IoT Core, you must create a configuration update for the shadow manager component that includes the `synchronize` parameter\. For more information, see [Sync local device shadows with AWS IoT Core](sync-shadows-with-iot-core.md)\.
- **Note**  <a name="note-requirement-enable-shadow-manager-client-devices"></a>
To enable a core device to interact with client device shadows, you must also configure and deploy the MQTT bridge component\. For more information, see [Enable shadow manager to communicate with client devices](work-with-client-device-shadows.md)\.
- **Note**  <a name="note-requirement-enable-shadow-manager-client-devices"></a>
To enable a core device to interact with client device shadows, you must also configure and deploy the MQTT bridge component\. For more information, see [Enable shadow manager to communicate with client devices](work-with-client-device-shadows.md)\.


## Sync local device shadows with AWS IoT Core

- **Note**  <a name="note-requirement-enable-shadow-manager-client-devices"></a>
To enable a core device to interact with client device shadows, you must also configure and deploy the MQTT bridge component\. For more information, see [Enable shadow manager to communicate with client devices](work-with-client-device-shadows.md)\.

