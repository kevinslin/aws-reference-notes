---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ecs-developer-guide.git)
{% endhint %}

## Tutorial: Creating a cluster with a Fargate Linux task using the AWS CLI

- **Note**  
The benefit of using the `default` cluster that is provided for you is that you don't have to specify the `--cluster cluster_name` option in the subsequent commands\. If you do create your own, non\-default, cluster, you must specify `--cluster cluster_name` for each command that you intend to use with that cluster\.


## Tutorial: Creating a cluster with a Fargate Windows task using the AWS CLI

- **Note**  
The benefit of using the `default` cluster that is provided for you is that you don't have to specify the `--cluster cluster_name` option in the subsequent commands\. If you do create your own, non\-default, cluster, you must specify `--cluster cluster_name` for each command that you intend to use with that cluster\.


## Tutorial: Creating a cluster with an EC2 task using the AWS CLI

- **Note**  
The benefit of using the `default` cluster that is provided for you is that you don't have to specify the `--cluster cluster_name` option in the subsequent commands\. If you do create your own, non\-default, cluster, you must specify `--cluster cluster_name` for each command that you intend to use with that cluster\.


## Tutorial: Specifying Sensitive Data Using Secrets Manager Secrets

- **Note**  
Alternatively, you can list all environment variables in your container using the `env` \(or `printenv`\) command\.


## Tutorial: Creating a service using a blue/green deployment

- **Note**  
Support for performing a blue/green deployment has been added for AWS CloudFormation\. For more information, see [Perform Amazon ECS blue/green deployments through CodeDeploy using AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/blue-green.html) in the *AWS CloudFormation User Guide*\.


## Tutorial: Listening for Amazon ECS CloudWatch Events

- **Note**  
When you use the AWS Management Console to create an event rule, the console automatically adds the IAM permissions necessary to grant CloudWatch Events permission to call your Lambda function\. If you are creating an event rule using the AWS CLI, you need to grant this permission explicitly\. For more information, see [Events and Event Patterns](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/CloudWatchEventsandEventPatterns.html) in the *Amazon CloudWatch Events User Guide*\.


## Tutorial: Using Amazon EFS

- **Note**  
Amazon EFS may not be available in all Regions\. For more information about which Regions support Amazon EFS, see [Amazon Elastic File System Endpoints and Quotas](https://docs.aws.amazon.com/general/latest/gr/elasticfilesystem.html) in the *AWS General Reference*\.
- **Note**  
If you do not see the message, make sure that the security group for your container instance allows inbound network traffic on port 80\.


## Tutorial: Using FSx for Windows File Server

- **Note**  
FSx for Windows File Server might not be available in all Regions\. For more information about which Regions support FSx for Windows File Server, see [Amazon FSx Endpoints and Quotas](https://docs.aws.amazon.com/general/latest/gr/fsxn.html) in the *AWS General Reference*\.
- **Note**  
You might not be able to connect to the website from within a VPN\.
- **Note**  
It takes 20 to 45 minutes to delete the FSx for Windows File Server file system or the AD\. You must wait until the FSx for Windows File Server file system delete operations are complete before starting the AD delete operations\.


## Tutorial: Deploying Fluent Bit on Amazon ECS for Windows containers

- **Note**  
This task definition exposes Fluent Bit container port 24224 to the host port 24224\. Verify that this port is not open in your EC2 instance security group to prevent access from outside\.
- **Note**  
This task uses the `default` network mode\. However, you can also use the `awsvpc` network mode with the task\.

