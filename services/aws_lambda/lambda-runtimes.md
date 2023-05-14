---
id: Lambda runtimes
title: Lambda runtimes
created: 1683841041000
updated: 1683841041000
---
# Lambda runtimes

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}

## Runtime modifications

- **Note**  
Invocations may fail if the wrapper script does not successfully start the runtime process\.


## Tutorial – Custom runtime

- **Note**  
On Windows, some Bash CLI commands that you commonly use with Lambda \(such as `zip`\) are not supported by the operating system's built\-in terminals\. To get a Windows\-integrated version of Ubuntu and Bash, [install the Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install-win10)\.
- **Note**  
Runtimes have additional responsibilities, including error handling, and providing context information to the handler\. For details, see [Building a custom runtime](runtimes-custom.md#runtimes-custom-build)\.


## AVX2 vectorization

- **Note**  
Lambda arm64 uses NEON SIMD architecture and does not support the x86 AVX2 extensions\.

