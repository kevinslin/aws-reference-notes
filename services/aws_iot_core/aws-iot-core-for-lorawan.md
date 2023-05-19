---
id: AWS IoT Core for LoRaWAN
title: AWS IoT Core for LoRaWAN
created: 1683841041000
updated: 1683841041000
---
# AWS IoT Core for LoRaWAN

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Configure position information for LoRaWAN devices and gateways

- **Note**  
The GNSS solver can only be used with LoRaWAN devices that have the LoRa Edge chip\. It can't be used with LoRaWAN gateways\. For gateways, you can still specify the static position information and add a destination that defines the AWS IoT rule for routing the position data when it's updated\.
- **Note**  
You can configure your resource position only when adding your gateway or device to AWS IoT Core for LoRaWAN\. This feature isn't available when onboarding your resource to AWS IoT Core for LoRaWAN\.


## Connecting to AWS IoT Core for LoRaWAN through a VPC interface endpoint

- **Note**  
AWS PrivateLink support for the endpoints is available only in US East \(N\. Virginia\) and Europe \(Ireland\)\.
+


## Managing gateways with AWS IoT Core for LoRaWAN

- **Note**  
If you have a gateway that is not listed in the Partner Catalog as a qualified gateway with AWS IoT Core for LoRaWAN, you might still be able to use it if the gateway is running LoRa Basics Station software with version 2\.0\.4 and later\. Make sure that you use **TLS Server and Client Authentication** for authenticating your LoRaWAN gateway\.

