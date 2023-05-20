---
id: AWS IoT secure tunneling
title: AWS IoT secure tunneling
created: 1683841041000
updated: 1683841041000
---
# AWS IoT secure tunneling

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Configuring a remote device and using IoT agent

- **Note**  
If you want to deliver the destination client access token to the remote device through methods other than subscribing to the reserved MQTT topic, you might need a destination client access token \(CAT\) listener and a local proxy\. The CAT listener must work with your chosen client access token delivery mechanism and be able to start a local proxy in destination mode\.


## Resolving secure tunneling connectivity issues

- **Note**  
If you're not sure whether the CAT needs to be rotated on the source or destination, you can rotate the CAT on both the source and destination by setting `ClientMode` to ALL when using the `RotateTunnelAccessToken` API\.
Rotating the CAT doesn't extend the tunnel duration\. For example, say the tunnel duration is 12 hours and the tunnel has already been open for 4 hours\. When you rotate the access tokens, the new tokens that are generated can only be used for the remaining 8 hours\.
- **Note**  
Using client tokens to reuse the CAT is not recommended\. We recommend that you use the `RotateTunnelAccessToken` API instead to rotate the client access tokens to reconnect to the tunnel\.

