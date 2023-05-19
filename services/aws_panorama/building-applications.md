---
id: Building applications
title: Building applications
created: 1683841041000
updated: 1683841041000
---
# Building applications

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-panorama-developer-guide.git)
{% endhint %}

## Models

- **Note**  
For a list of pre\-built models that have been tested with AWS Panorama, see [Model compatibility](https://github.com/awsdocs/aws-panorama-developer-guide/blob/main/resources/model-compatibility.md)\.
- **Note**  
For details about the framework versions and file formats supported by SageMaker Neo, see [Supported Frameworks](https://docs.aws.amazon.com/sagemaker/latest/dg/neo-supported-devices-edge-frameworks.html) in the Amazon SageMaker Developer Guide\.
- **Note**  
Specify the framework version's major and minor version only\. For a list of supported PyTorch, Apache MXNet, and TensorFlow versions versions, see [Supported frameworks](https://docs.aws.amazon.com/sagemaker/latest/dg/neo-supported-devices-edge-frameworks.html)\.


## Application SDK

- **Note**  
To ensure that you have access to the latest functionality of the AWS Panorama Application SDK, [upgrade the appliance software](appliance-manage.md#appliance-manage-software)\.


## Serving inbound traffic

- **Important**  
By default, the AWS Panorama Appliance does not accept incoming traffic on any ports\. Opening ports on the appliance has implicit security risk\. When you use this feature, you must take additional steps to [secure your appliance from external traffic](appliance-network.md) and secure communications between authorized clients and the appliance\.  
The sample code included with this guide is for demonstration purposes and does not implement authentication, authorization, or encryption\.
- **Important**  
The sample implementation is not secure for production use\. To avoid making your appliance vulnerable to attacks, you must implement appropriate security controls in your code and network configuration\.


## Using the GPU

- **Important**  
If you enable GPU access, you can't run model nodes in any application on the appliance\. For security purposes, GPU access is restricted when the appliance runs a model compiled with SageMaker Neo\. With GPU access, you must run your models in application code nodes, and all applications on the device share access to the GPU\.


## Tutorial – Windows development environment

- **Note**  
Docker Desktop only enables Docker in the default distribution\. If you have other Linux distributions installed prior to running this tutorial, enable Docker in the newly installed Ubuntu distribution in the Docker Desktop settings menu under **Resources**, **WSL integration**\.
- **Note**  
To access files in your Windows installation from within Ubuntu, navigate to the `/mnt/c` directory\. For example, you can list files in your downloads directory by running `ls /mnt/c/Users/windows-username/Downloads`\.

