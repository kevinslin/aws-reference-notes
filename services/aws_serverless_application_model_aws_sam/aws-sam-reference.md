---
id: AWS SAM reference
title: AWS SAM reference
created: 1683841041000
updated: 1683841041000
---
# AWS SAM reference

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-sam-developer-guide.git)
{% endhint %}

## Installing Docker

- **Note**  
Docker is required only for testing your applications locally and for building deployment packages using the `--use-container` option\.
- **Note**  
On Linux, to build and run Lambda functions with a different instruction set architecture than your host machine, there are additional steps to configure Docker\. For example, to run `arm64` functions on an `x86_64` machine, you can run the following command to configure the Docker daemon: `docker run --rm --privileged multiarch/qemu-user-static --reset -p yes`\.
- **Note**  
Docker Desktop is officially supported, but starting with AWS SAM CLI version 1\.47\.0, you can use alternatives as long as they use the Docker runtime\.
- **Note**  
AWS SAM officially supports Docker Desktop\. However, starting with AWS SAM CLI version 1\.47\.0, you can use alternatives as long as they use the Docker runtime\.


## Installing Homebrew

- **Note**  
Installing Homebrew changes your environment's default Python version to the one that Homebrew installs\.


## Image repositories

- **Note**  
Prior to version 1\.22\.0 of the AWS SAM CLI, DockerHub was the default repository that the AWS SAM CLI pulled the container image from\. Starting with version 1\.22\.0, the default repository changed to Amazon Elastic Container Registry Public \(Amazon ECR Public\)\. To pull a container image from a repository other than the current default, you can use the [sam build](sam-cli-command-reference-sam-build.md) command with the \-\-build\-image option\. The examples at the end of this topic show how to build applications using DockerHub repository images\.
- **Note**  
Amazon ECR Public replaced DockerHub starting with the AWS SAM CLI version 1\.22\.0\. If you are using an earlier version of the AWS SAM CLI, we recommend that you upgrade\.


## Deploying gradually

- **Note**  
If you enable gradual deployments through your AWS SAM template, a CodeDeploy resource is automatically created for you\. You can view the CodeDeploy resource directly through the AWS Management Console\.


## Important notes

- **Important**  
Although the `pip install aws-sam-cli` command also works on 64\-bit Windows, we recommend that you use the [64\-bit MSI](https://github.com/aws/aws-sam-cli/releases/latest/download/AWS_SAM_CLI_64_PY3.msi) to install AWS SAM CLI on 64\-bit systems\.

