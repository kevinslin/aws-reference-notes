---
id: Device provisioning
title: Device provisioning
created: 1683841041000
updated: 1683841041000
---
# Device provisioning

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Provisioning devices that don't have device certificates using fleet provisioning

- **Important**  
Provisioning claim private keys should be secured at all times, including on the device\. We recommend that you use AWS IoT CloudWatch metrics and logs to monitor for indications of misuse\. If you detect misuse, turn off the provisioning claim certificate so it cannot be used for device provisioning\.
- **Important**  
You must manage the trusted user's access and permission to perform this procedure\. One way to do this is to provide and maintain an account for the trusted user that authenticates them and grants them access to the AWS IoT features and API operations required to perform this procedure\.


## Provisioning templates

- **Note**  
When you declare a certificate in a template, use only one of these methods\. For example, if you use a CSR, you cannot also specify a certificate ID or a device certificate\. For more information, see [X\.509 client certificates](x509-client-certs.md)\.
- **Note**  
If a `Policy` section is present, `PolicyName` or `PolicyDocument`, but not both, must be specified\.
- **Important**  
You must use `CertificateId` in a template that's used for JIT provisioning\.
- **Note**  
An existing provisioning template can be updated to add a [pre\-provisioning hook](pre-provisioning-hook.md)\.


## Pre-provisioning hooks

- **Important**  
Be sure to include the `source-arn` or `source-account` in the global condition context keys of the policies attached to your Lambda action to prevent permission manipulation\. For more information about this, see [Cross\-service confused deputy prevention](cross-service-confused-deputy-prevention.md)\.
- **Note**  
If the Lambda function fails, the provisioning request fails with `ACCESS_DENIED` and an error is logged to CloudWatch Logs\.
If the Lambda function doesn't return `"allowProvisioning": "true"` in the response, the provisioning request fails with `ACCESS_DENIED`\.
The Lambda function must finish running and return within 5 seconds, otherwise the provisioning request fails\.


## Creating IAM policies and roles for a user installing a device

- **Note**  
These procedures are for use only when directed by the AWS IoT console\.  
To go to this page from the console, open [create a new provisioning template](https://console.aws.amazon.com/iot/home#/provisioningtemplate/create/provisioningmethods/trustedUser)\.


## Device provisioning MQTT API

- **Important**  
Before publishing a request message topic, subscribe to the response topics to receive the response\. The messages used by this API use MQTT's publish/subscribe protocol to provide a request and response interaction\.   
If you do not subscribe to the response topics *before* you publish a request, you might not receive the results of that request\.
- **Note**  
For security, the `certificateOwnershipToken` returned by `CreateCertificateFromCsr` expires after one hour\. `RegisterThing` must be called before the `certificateOwnershipToken` expires\. If the certificate created by `CreateCertificateFromCsr` has not been activated and has not been attached to a policy or a thing by the time the token expires, the certificate is deleted\. If the token expires, the device can call `CreateCertificateFromCsr` to generate a new certificate\.
- **Note**  
For security, the `certificateOwnershipToken` returned by `CreateKeysAndCertificate` expires after one hour\. `RegisterThing` must be called before the `certificateOwnershipToken` expires\. If the certificate created by `CreateKeysAndCertificate` has not been activated and has not been attached to a policy or a thing by the time the token expires, the certificate is deleted\. If the token expires, the device can call `CreateKeysAndCertificate` to generate a new certificate\.

