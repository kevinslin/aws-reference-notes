---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-sam-developer-guide.git)
{% endhint %}

## Installing the AWS SAM CLI

- **Important**  
You must have Homebrew installed on your Linux machine\. For install instructions, see [Installing Homebrew to use with the AWS SAM CLI](install-homebrew.md)\.
- **Note**  
 To invoke the AWS SAM CLI with the sam command, the installer automatically creates a symlink between `/usr/local/bin/sam` and `/usr/local/aws-sam-cli/sam`\.
- **Important**  
You must have Homebrew installed on your machine\. For install instructions, see [Installing Homebrew to use with the AWS SAM CLI](install-homebrew.md)\.


## Tutorial: Hello World application

- **Note**  
 If you don't have Python on your local machine, use the sam build \-\-use\-container  command instead\. The AWS SAM CLI will create a Docker container that includes your function's runtime and dependencies\. This command requires Docker on your local machine\. To install Docker, see [Installing Docker](install-docker.md)\.
- **Note**  
This step requires AWS credentials configuration\. For more information, see [Step 5: Use the AWS CLI to configure AWS credentials](prerequisites.md#prerequisites-configure-credentials) in [AWS SAM prerequisites](prerequisites.md)\.
- **Note**  
This step is optional since it requires Docker on your local machine\.
- **Important**  
To use the AWS SAM CLI for local testing, you must have Docker installed and configured\. For more information, see [Installing Docker](install-docker.md)\.

