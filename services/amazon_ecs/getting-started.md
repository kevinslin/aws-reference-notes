---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ecs-developer-guide.git)
{% endhint %}
## Set up

- **Note**  
The Amazon ECS console first\-run experience creates a VPC for your cluster, so if you intend to use the Amazon ECS console, you can skip to the next section\.
- **Important**  
If your account supports Amazon EC2 Classic in a region, then you do not have a default VPC in that region\.
- **Note**  
The Amazon ECS classic console first run experience creates a security group for your instances and load balancer based on the task definition you use, so if you intend to use the Amazon ECS console, you can move ahead to the next section\.
- **Tip**  
You need the public IP address of your local computer, which you can get using a service\. For example, we provide the following service: [http://checkip\.amazonaws\.com/](http://checkip.amazonaws.com/) or [https://checkip\.amazonaws\.com/](https://checkip.amazonaws.com/)\. To locate another service that provides your IP address, use the search phrase "what is my IP address\." If you are connecting through an internet service provider \(ISP\) or from behind a firewall without a static IP address, you must find out the range of IP addresses used by client computers\.


## Creating a container image

- **Important**  
AWS and Docker have collaborated to make a simplified developer experience that allows you to deploy and manage containers on Amazon ECS directly using Docker tools\. You can now build and test your containers locally using Docker Desktop and Docker Compose, and then deploy them to Amazon ECS on Fargate\. To get started with the Amazon ECS and Docker integration, download Docker Desktop and optionally sign up for a Docker ID\. For more information, see [Docker Desktop](https://www.docker.com/products/docker-desktop) and [Docker ID signup](https://hub.docker.com/signup/awsedge?utm_source=awsedge)\.
- **Important**  
This step assumes you are using the Amazon Linux 2 AMI for your instance\. For all other operating systems, see [Docker Desktop overview](https://docs.docker.com/desktop/)\.
- **Note**  
In some cases, you may need to reboot your instance to provide permissions for the `ec2-user` to access the Docker daemon\. Try rebooting your instance if you see the following error:
- **Note**  
Output from the Apache web server is displayed in the terminal window\. You can ignore the "`Could not reliably determine the server's fully qualified domain name`" message\.
- **Important**  
If you receive an error, install or upgrade to the latest version of the AWS CLI\. For more information, see [Installing the AWS Command Line Interface](https://docs.aws.amazon.com/cli/latest/userguide/installing.html) in the *AWS Command Line Interface User Guide*\.


## Using the AWS CDK

- **Note**  
These instructions assume you are using AWS CDK v2\.
- **Note**  
The AWS CDK application template uses the name of the project directory to generate names for source files and classes\. In this example, the directory is named `hello-ecs`\. If you use a different project directory name, your app won't match these instructions\.
- **Note**  
A stack is a unit of deployment\. All resources must be in a stack, and all the resources that are in a stack are deployed at the same time\. If a resource fails to deploy, any other resources that were already deployed are rolled back\. An AWS CDK app can contain multiple stacks, and resources in one stack can refer to resources in another stack\.


## Using the console with Windows containers on AWS Fargate

- **Note**  
It can take up to 15 minutes for your container instance to download and extract the Windows container base layers\.

