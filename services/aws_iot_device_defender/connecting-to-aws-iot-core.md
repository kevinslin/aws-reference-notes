---
id: Connecting to AWS IoT Core
title: Connecting to AWS IoT Core
created: 1683841041000
updated: 1683841041000
---
# Connecting to AWS IoT Core

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Connecting to AWS IoT Core service endpoints

- **Note**  
IoT devices should use [AWS IoT Device SDKs](iot-connect-devices.md#iot-connect-device-sdks)\. The Device SDKs are optimized for use on devices, support MQTT communication with AWS IoT, and support the AWS IoT APIs most used by devices\. For more information about the Device SDKs and the features they provide, see [AWS IoT Device SDKs](iot-connect-devices.md#iot-connect-device-sdks)\.  
Mobile devices should use [AWS Mobile SDKs](#iot-connect-mobile-sdks)\. The Mobile SDKs provide support for AWS IoT APIs, MQTT device communications, and the APIs of other AWS services on mobile devices\. For more information about the Mobile SDKs and the features they provide, see [AWS Mobile SDKs](#iot-connect-mobile-sdks)\.


## Connecting devices to AWS IoT

- **Important**  
This SDK is intended for use by experienced embedded\-software developers\.


## Connecting to AWS IoT FIPS endpoints

- **Note**  
AWS IoT doesn't support AWS account\-specific **AWS IoT Core \- data plane** endpoints that are FIPS\-compliant\. Service features that require an AWS account\-specific endpoint in the [Server Name Indication \(SNI\)](transport-security.md) can't be used\. FIPS\-compliant **AWS IoT Core \- data plane** endpoints can't support [Multi\-Account Registration Certificates](x509-client-certs.md#multiple-account-cert), [Custom Domains](iot-custom-endpoints-configurable-custom.md), and [Custom Authorizers](custom-authentication.md)\.

