---
id: AWSTOE component manager
title: AWSTOE component manager
created: 1683841041000
updated: 1683841041000
---
# AWSTOE component manager

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/ec2-image-builder-user-guide.git)
{% endhint %}

## Get started with AWSTOE

- **Important**  
AWSTOE is invoked directly from its download location\. There is no need for a separate install step\. This also means that AWSTOE can make changes to the local environment\.  
To ensure that you isolate changes during component development, we recommend that you use an EC2 instance to develop and test AWSTOE components\.
- **Note**  
The AWSTOE application can validate only the component syntax for the current operating system\. For example, when running `awstoe.exe` on Windows, you cannot validate the syntax for a Linux document that uses the `ExecuteBash` action module\.


## Use component documents

- **Tip**  
The service that uses your component to build an image might implement rules about what phases to use for their build process, and when those phases are allowed to run\. This is important to consider when you design your component\.
- **Note**  
The log folder might also contain other temporary files that are not covered here\.


## Action modules

- **Note**  
All action modules use the same account as the Systems Manager agent when they run, which is `root` on Linux, and `NT Authority\SYSTEM` on Windows\.
- **Note**  
All folders in the destination path must exist prior to download, or the download fails\.
- **Note**  
For the following examples, the Windows folder path can be replaced with a Linux path\. For example, `C:\myfolder\package.zip` can be replaced with `/myfolder/package.zip`\.


## STIG components

- **Note**  
The STIG\-Build\-Windows\-Medium components include all STIG settings that AWSTOE applies for STIG\-Build\-Windows\-Low components, in addition to the STIG settings that apply specifically for Category II vulnerabilities\.
- **Note**  
The STIG\-Build\-Windows\-High components include all STIG settings that AWSTOE applies for STIG\-Build\-Windows\-Low and STIG\-Build\-Windows\-Medium components, in addition to the STIG settings that apply specifically for Category I vulnerabilities\.
- **Note**  
The STIG\-Build\-Linux\-Medium components include all STIG settings that AWSTOE applies for STIG\-Build\-Linux\-Low components, in addition to the STIG settings that apply specifically for Category II vulnerabilities\.
- **Note**  
The STIG\-Build\-Linux\-High components include all STIG settings that AWSTOE applies for STIG\-Build\-Linux\-Low and STIG\-Build\-Linux\-Medium components, in addition to the STIG settings that apply specifically for Category I vulnerabilities\.
- **Note**  
You can review the reports with one of the [STIG Viewing Tools](https://public.cyber.mil/stigs/srg-stig-tools/)\. These tools are available online via the DoD Cyber Exchange\.
- **Note**  
AWSTOE currently supports SCAP compliance validation for Windows Server 2012 R2, 2016, and 2019\.
- **Note**  
AWSTOE currently supports SCAP compliance validation for RHEL 7/8 and Ubuntu 18\. The SCC application currently supports the x86 architecture for validation\.


## Command reference

- **Note**  
Some AWSTOE action modules require elevated permissions to run on a Linux server\. To use elevated permissions, prefix the command syntax with sudo, or run the sudo su command one time when you log in before running the commands linked below\. For more information about AWSTOE action modules, see [Action modules supported by AWSTOE component manager](toe-action-modules.md)\.

