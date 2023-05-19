---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloudhsm-user-guide.git)
{% endhint %}

## Create a VPC

- **Note**  
Following these steps will result in the creation of public and private subnets\.


## Create a cluster

- **Important**  
When you create a cluster, AWS CloudHSM creates a [service\-linked role](https://docs.aws.amazon.com/IAM/latest/UserGuide/using-service-linked-roles.html) named AWSServiceRoleForCloudHSM\. If AWS CloudHSM cannot create the role or the role does not already exist, you may not be able to create a cluster\. For more information, see [Resolving cluster creation failures](troubleshooting-create-cluster.md)\. For more information about service–linked roles, see [Service\-linked roles for AWS CloudHSM](service-linked-roles.md)\.


## Launch an EC2 client

- **Note**  
 Your EC2 instance can run all of the AWS CLI commands contained in this guide\. If the AWS CLI is not installed, you can download it from [AWS Command Line Interface](https://aws.amazon.com/cli/)\. If you are using Windows, you can download and run a 64\-bit or 32\-bit Windows installer\. If you are using Linux or macOS, you can install the CLI using pip\.


## Configure EC2 instance security groups

- **Note**  
 You can assign a maximum of five security groups to an Amazon EC2 instance\. If you have reached the maximum limit, you must modify the default security group of the Amazon EC2 instance and the cluster security group:  
In the default security group, do the following:  
Add an outbound rule to permit traffic on all ports to `0.0.0.0/0`\.
Add an inbound rule to permit traffic using the TCP protocol over ports `2223-2225` from the cluster security group\.
In the cluster security group, do the following:  
Add an outbound rule to permit traffic on all ports to `0.0.0.0/0`\.
Add an inbound rule to permit traffic using the TCP protocol over ports `2223-2225` from the default security group\.


## Verify HSM identity (optional)

- **Note**  
This process is optional\. However, it works only until a cluster is initialized\. After the cluster is initialized, you cannot use this process to get the certificates or verify the HSMs\.


## Initialize the cluster

- **Note**  
Before you initialize the cluster, review the process by which you can [verify the identity and authenticity of the HSMs](verify-hsm-identity.md)\. This process is optional and works only until a cluster is initialized\. After the cluster is initialized, you cannot use this process to get your certificates or verify the HSMs\.
- **Important**  
To initialize your cluster, your trust anchor must comply with [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) and meet the following requirements:   
If using X509v3 extensions, the X509v3 Basic Constraints extension must be present\.
The trust anchor must be a self\-signed certificate\.
Extension values must not conflict with each other\.
- **Note**  
For a production cluster, the key you are about to create should be created in a secure manner using a trusted source of randomness\. We recommend that you use a secured offsite and offline HSM or the equivalent\. Store the key safely\. If you can demonstrate that you own the key, you can also demonstrate that you own the cluster and the data it contains\.  
For development and testing, you can use any convenient tool \(such as OpenSSL\) to create and sign the cluster certificate\. The following example shows you how to create a key\. After you have used the key to create a self\-signed certificate \(see below\), you should store it in a safe manner\. To sign into your AWS CloudHSM instance, the certificate must be present, but the private key does not\.


## Activate the cluster

- **Important**  
Before you can activate the cluster, you must first copy the issuing certificate to the default location for the platform on each EC2 instance that connects to the cluster \(you create the issuing certificate when you initialize the cluster\)\.  
Linux


## Build an application

- **Note**  
If using Client SDK 3, use [CloudHSM Management Utility \(CMU\)](cloudhsm_mgmt_util.md) instead of CloudHSM CLI\.

