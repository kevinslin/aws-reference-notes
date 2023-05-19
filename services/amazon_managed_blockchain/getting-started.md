---
id: Getting Started
title: Getting Started
created: 1683841041000
updated: 1683841041000
---
# Getting Started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-managed-blockchain-management-guide.git)
{% endhint %}

## Prerequisites and Considerations

- **Important**  
This security group configuration is recommended for this tutorial only\. Carefully consider security group settings for your desired security posture\. For information about the minimum required rules, see [Configuring Security Groups for Hyperledger Fabric on Amazon Managed Blockchain](managed-blockchain-security-sgs.md)\.


## Step 4: Set Up a Client

- **Note**  
An AWS CloudFormation template to create a Hyperledger Fabric client is available in [amazon\-managed\-blockchain\-client\-templates repository](https://github.com/awslabs/amazon-managed-blockchain-client-templates) on Github\. For more information, see the [readme\.md](https://github.com/awslabs/amazon-managed-blockchain-client-templates/blob/master/README.md) in that repository\. For more information about using AWS CloudFormation, see [Getting Started](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/GettingStarted.Walkthrough.html) in the *AWS CloudFormation User Guide*\.
- **Note**  
If you are working with Hyperledger Fabric v1\.2 networks, you need to install and build the correct client version, which is available at https://github\.com/hyperledger/fabric\-ca/releases/download/v1\.2\.1/hyperledger\-fabric\-ca\-linux\-amd64\-1\.2\.1\.tar\.gz\.
- **Note**  
If you are working with Hyperledger Fabric v1\.2 networks, use `--branch v1.2.0` instead of `--branch v1.4.7` in the following commmands\.
- **Note**  
If you are working with Hyperledger Fabric v1\.2 networks, use `image: hyperledger/fabric-tools:1.2` in the following example instead of `image: hyperledger/fabric-tools:1.4`\. In addition, use `CORE_LOGGING_LEVEL=info` instead of `FABRIC_LOGGING_SPEC=info`\.


## Step 5: Enroll the Member Admin

- **Important**  
It may take a minute or two after you enroll for you to be able to use your administrator certificate to create a channel with the ordering service\.


## Step 6: Create a Channel

- **Note**  
All Hyperledger Fabric networks on Managed Blockchain support a maximum of 8 channels per network, regardless of network edition\.
- **Important**  
This file is sensitive\. Artifacts from pasting can cause the file to fail with marshalling errors\. We recommend using `emacs` to edit it\. You can also use `VI`, but before using `VI`, enter `:set paste`, press `i` to enter insert mode, paste the contents, press escape, and then enter `:set nopaste` before saving\.
- **Important**  
Hyperledger Fabric 1\.4 requires that a channel ID contain only lowercase ASCII alphanumeric characters, dots \(\.\), and dashes \(\-\)\. It must start with a letter, and must be fewer than 250 characters\.


## Step 8: Invite a Member and Create a Multi-Member Channel

- **Important**  
This file is sensitive\. Artifacts from pasting can cause the file to fail with marshalling errors\. We recommend using `emacs` to edit it\. You can also use `VI`, but before using `VI`, enter `:set paste`, press `i` to enter insert mode, paste the contents, press escape, and then enter `:set nopaste` before saving\.

