---
id: MQTT-based file delivery
title: MQTT-based file delivery
created: 1683841041000
updated: 1683841041000
---
# MQTT-based file delivery

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-docs.git)
{% endhint %}

## Managing a stream in the AWS Cloud

- **Note**  
At this time, streams are not visible in the AWS Management Console\. You must use the AWS CLI or AWS SDK to manage a stream in AWS IoT\.
- **Note**  
The endpoint of the AWS IoT data plane is specific to the AWS account and Region\. You must use the endpoint for the AWS account and the Region in which your devices are registered in AWS IoT\.


## Using AWS IoT MQTT-based file delivery in devices

- **Note**  
You don't need to use the `DescribeStream` API if your device receives all required stream file IDs in the initial data set\.
- **Note**  
If you replace `json` with `cbor` in the topics and topic filters shown, your device receives messages in the CBOR format, which is more compact than JSON\.
- **Note**  
If you replace "json" with "cbor" in the topics and topic filters shown, your device will receive messages in the CBOR format, which is more compact than JSON\.
AWS IoT MQTT\-based file delivery limits the size of a block to 128 KB\. If you make a request for a block that is more than 128 KB, the request will fail\.
You can make a request for multiple blocks whose total size is greater than 128 KB \(for example, if you make a request for 5 blocks of 32 KB each for a total of 160 KB of data\)\. In this case, the request doesn't fail, but your device must make multiple requests in order to receive all of the data requested\. The service will send additional blocks as your device makes additional requests\. We recommend that you continue with a new request only after the previous response has been correctly received and processed\.
Regardless of the total size of data requested, you should program your device to initiate retries when blocks are not received, or not received correctly\.
- **Important**  
Either "`n`" or "`b`" should be specified\. If neither of them is specified, the `GetStream` request might not be valid when the file size is less than 131072 bytes \(128 KB\)\.
- **Note**  
For backward compatibility, fields in the error response may be in non\-abbreviated form\. For example, the error code might be designated by either "code" or "o" fields and the client token field may be designated by either "clientToken" or "c" fields\. We recommend that you use the abbreviation form shown above\.

