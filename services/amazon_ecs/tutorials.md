---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials
## Tutorial: Creating a cluster with a Fargate Linux task using the AWS CLI

- **Note**  
The benefit of using the `default` cluster that is provided for you is that you don't have to specify the `--cluster cluster_name` option in the subsequent commands\. If you do create your own, non\-default, cluster, you must specify `--cluster cluster_name` for each command that you intend to use with that cluster\.


## Tutorial: Creating a cluster with a Fargate Windows task using the AWS CLI

- **Note**  
The benefit of using the `default` cluster that is provided for you is that you don't have to specify the `--cluster cluster_name` option in the subsequent commands\. If you do create your own, non\-default, cluster, you must specify `--cluster cluster_name` for each command that you intend to use with that cluster\.


## Tutorial: Creating a service using a blue/green deployment

- **Note**  
Support for performing a blue/green deployment has been added for AWS CloudFormation\. For more information, see [Perform Amazon ECS blue/green deployments through CodeDeploy using AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/blue-green.html) in the *AWS CloudFormation User Guide*\.


## Tutorial: Listening for Amazon ECS CloudWatch Events

- **Note**  
When you use the AWS Management Console to create an event rule, the console automatically adds the IAM permissions necessary to grant CloudWatch Events permission to call your Lambda function\. If you are creating an event rule using the AWS CLI, you need to grant this permission explicitly\. For more information, see [Events and Event Patterns](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/CloudWatchEventsandEventPatterns.html) in the *Amazon CloudWatch Events User Guide*\.


## Tutorial: Deploying Fluent Bit on Amazon ECS for Windows containers

- **Note**  
This task definition exposes Fluent Bit container port 24224 to the host port 24224\. Verify that this port is not open in your EC2 instance security group to prevent access from outside\.
- **Note**  
This task uses the `default` network mode\. However, you can also use the `awsvpc` network mode with the task\.

