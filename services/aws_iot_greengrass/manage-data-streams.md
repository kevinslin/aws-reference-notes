---
id: Manage data streams
title: Manage data streams
created: 1683841041000
updated: 1683841041000
---
# Manage data streams

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Use StreamManagerClient to work with streams

- **Note**  
<a name="stream-manager-clients"></a>Typically, clients of stream manager are user\-defined Greengrass components\. If your business case requires it, you can also allow non\-component processes running on the Greengrass core \(for example, a Docker container\) to interact with stream manager\. For more information, see [Client authentication](manage-data-streams.md#stream-manager-security-client-authentication)\.
- **Note**  
If you do instantiate `StreamManagerClient` in the handler, you must explicitly call the `close()` method when the `client` completes its work\. Otherwise, the `client` keeps the connection open and another thread running until the script exits\.
- **Note**  
<a name="streammanagerclient-http-config"></a>`StreamManagerClient` also provides a target destination you can use to export streams to an HTTP server\. This target is intended for testing purposes only\. It is not stable or supported for use in production environments\.
- **Note**  
<a name="BatchPutAssetPropertyValue-data-reqs"></a>When you send data to AWS IoT SiteWise, your data must meet the requirements of the `BatchPutAssetPropertyValue` action\. For more information, see [BatchPutAssetPropertyValue](https://docs.aws.amazon.com/iot-sitewise/latest/APIReference/API_BatchPutAssetPropertyValue.html) in the *AWS IoT SiteWise API Reference*\.

