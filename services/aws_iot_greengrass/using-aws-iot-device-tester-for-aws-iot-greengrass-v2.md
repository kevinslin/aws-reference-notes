---
id: Using AWS IoT Device Tester for AWS IoT Greengrass V2
title: Using AWS IoT Device Tester for AWS IoT Greengrass V2
created: 1683841041000
updated: 1683841041000
---
# Using AWS IoT Device Tester for AWS IoT Greengrass V2

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Supported versions

- **Note**  
<a name="unzip-package-to-local-drive"></a>IDT does not support being run by multiple users from a shared location, such as an NFS directory or a Windows network shared folder\. We recommend that you extract the IDT package to a local drive and run the IDT binary on your local workstation\.


## Download IDT for AWS IoT Greengrass V2

- **Note**  
<a name="unzip-package-to-local-drive"></a>IDT does not support being run by multiple users from a shared location, such as an NFS directory or a Windows network shared folder\. We recommend that you extract the IDT package to a local drive and run the IDT binary on your local workstation\.


## Use IDT to run the AWS IoT Greengrass qualification suite

- **Important**  
IDT supports the four latest `major.minor` versions of the Greengrass qualification suite versions to generate qualification reports that you can submit to AWS Partner Network to include your devices in the AWS Partner Device Catalog\. Tests from unsupported test suite versions are not valid for device qualification\. IDT doesn't print qualification reports for unsupported versions\. For more information, see [Support policy for AWS IoT Device Tester for AWS IoT Greengrass](idt-support-policy.md)\.  
You can run `list-supported-products` to list the versions of AWS IoT Greengrass and test suites that are supported by your current version of IDT\.


## Use IDT to develop and run your own test suites

- **Note**  
<a name="unzip-package-to-local-drive"></a>IDT does not support being run by multiple users from a shared location, such as an NFS directory or a Windows network shared folder\. We recommend that you extract the IDT package to a local drive and run the IDT binary on your local workstation\.  
Windows has a path length limitation of 260 characters\. If you are using Windows, extract IDT to a root directory like `C:\ ` or `D:\` to keep your paths under the 260 character limit\.


## Troubleshooting IDT for AWS IoT Greengrass V2

- **Note**  
`user` and `username` refer to the SSH user used by IDT to access the device under test\.

