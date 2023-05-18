---
id: Building
title: Building
created: 1683841041000
updated: 1683841041000
---
# Building

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-sam-developer-guide.git)
{% endhint %}

## Building applications

- **Note**  
If you specify a multi\-architecture base image in your Dockerfile, AWS SAM builds your container image for your host machine's architecture\. To build for a different architecture, specify a base image that uses the specific target architecture\.


## Building layers

- **Note**  
When you create a custom layer, AWS Lambda depends on environment variables to find your layer code\. Lambda runtimes include paths in the `/opt` directory where your layer code is copied into\. Your project's build artifact folder structure must match the runtime's expected folder structure so your custom layer code can be found\.  
For example, for Python you can place your code in the `python/` subdirectory\. For NodeJS, you can place your code in the `nodejs/node_modules/` subdirectory\.  
For more information, see [Including library dependencies in a layer](https://docs.aws.amazon.com/lambda/latest/dg/configuration-layers.html#configuration-layers-path) in the *AWS Lambda Developer Guide*\.
- **Note**  
If you don't include the `Metadata` resource attribute section, AWS SAM doesn't build the layer\. Instead, it copies the build artifacts from the location specified in the `CodeUri` property of the layer resource\. For more information, see the [ContentUri](sam-resource-layerversion.md#sam-layerversion-contenturi) property of the `AWS::Serverless::LayerVersion` resource type\.


## Building custom runtimes

- **Note**  
We recommend building Lambda functions with Cargo Lambda\. To learn more, see [Building Rust Lambda functions with Cargo Lambda](building-rust.md)\.

