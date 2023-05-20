---
id: Device Shadow service
title: Device Shadow service
created: 1683841041000
updated: 1683841041000
---
# Device Shadow service

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Using shadows in devices

- **Important**  
Because MQTT uses a publish/subscribe communication model, you should subscribe to the response topics *before* you publish a request topic\. If you don't, you might not receive the response to the request that you publish\.   
If you use an [AWS IoT Device SDK](iot-sdks.md) to call the Device Shadow service APIs, this is handled for you\.
- **Important**  
Make sure that your app's or service's use of the shadows is consistent and supported by the corresponding implementations in your devices\. For example, consider how shadows are created, updated, and deleted\. Also consider how updates are handled in the device and the apps or services that access the device through a shadow\. Your design should be clear about how the device's state is updated and reported and how your apps and services interact with the device and its shadows\.


## Using shadows in apps and services

- **Important**  
Make sure that your app's or service's use of the shadows is consistent with and supported by the corresponding implementations in your devices\. Consider, for example, how shadows are created, updated, and deleted, and how updates are handled in the device and the apps or services that access the shadow\. Your design should clearly specify how the device's state is updated and reported, and how your apps and services interact with the device and its shadows\.
- **Note**  
MQTT LWT messages sent to AWS IoT reserved topics \(topics that begin with $\) are ignored by the AWS IoT Device Shadow service\. However, they are processed by subscribed clients and by the AWS IoT rules engine, so you will need to create an LWT message that is sent to a non\-reserved topic and a rule that republishes the MQTT LWT message as a shadow update message to the shadow's reserved update topic, `ShadowTopicPrefix/update`\.


## Interacting with shadows

- **Note**  
Setting the device's shadow state to `null` does not delete the shadow\. The shadow version will be incremented on the next update\.  
Deleting a device's shadow does not delete the thing object\. Deleting a thing object does not delete the corresponding device's shadow\.  
Deleting a shadow does not reset its version number to 0\.


## Device Shadow REST API

- **Note**  
To use the APIs, you must use `iotdevicegateway` as the service name for authentication\. For more information, see [IoTDataPlane](https://docs.aws.amazon.com/AWSJavaScriptSDK/v3/latest/clients/client-iot-data-plane/classes/iotdataplane.html)\.
- **Note**  
The unnamed \(classic\) shadow does not appear in this list\. The response is an empty list if you only have a classic shadow or if the `thingName` you specify doesn't exist\.


## Device Shadow service documents

- **Note**  
The client token can be no longer than 64 bytes\. A client token that is longer than 64 bytes causes a 400 \(Bad Request\) response and an *Invalid clientToken* error message\.

