---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codedeploy-user-guide.git)
{% endhint %}

## Step 1: Setting up

- **Important**  
We strongly recommend you set up a workforce identity \(a user managed in IAM Identity Center\) with the AWS CLI\. Many of the procedures in this guide assume you're using the AWS CLI to perform configurations\.
- **Important**  
If you configure the AWS CLI, you may be prompted to specify an AWS Region\. Choose one of the supported regions listed in [Region and endpoints](https://docs.aws.amazon.com/general/latest/gr/rande.html#codedeploy_region) in the *AWS General Reference*\.


## Step 2: Create a service role

- **Note**  
Do not use a comma after the last endpoint in the list\.
- **Important**  
Be sure to include `file://` before the file name\. It is required in this command\.


## Step 4: Create an IAM instance profile

- **Note**  
 If you are using the Amazon ECS or AWS Lambda compute platform , skip this step\. Amazon ECS deployments deploy an Amazon ECS service, and AWS Lambda deployments deploy a serverless Lambda function version, so an instance profile for Amazon EC2 instances is not required\.
- **Note**  
You can attach an IAM instance profile to an Amazon EC2 instance as you launch it or to a previously launched instance\. For more information, see [Instance profiles](https://docs.aws.amazon.com/IAM/latest/UserGuide/roles-usingrole-instanceprofile.html)\.
- **Note**  
We recommend that you restrict this policy to only those Amazon S3 buckets your Amazon EC2 instances must access\. Make sure to give access to the Amazon S3 buckets that contain the CodeDeploy agent\. Otherwise, an error might occur when the CodeDeploy agent is installed or updated on the instances\. To grant the IAM instance profile access to only some CodeDeploy resource kit buckets in Amazon S3, use the following policy, but remove the lines for buckets you want to prevent access to:
- **Note**  
If you want to use [ IAM authorization](https://docs.aws.amazon.com/IAM/latest/UserGuide/intro-structure.html#intro-structure-authorization) or Amazon Virtual Private Cloud \(VPC\) endpoints with CodeDeploy, you will need to add more permissions\. See [Use CodeDeploy with Amazon Virtual Private Cloud](https://docs.aws.amazon.com/codedeploy/latest/userguide/vpc-endpoints) for more information\.
- **Note**  
We recommend that you restrict this policy to only those Amazon S3 buckets your Amazon EC2 instances must access\. Make sure to give access to the Amazon S3 buckets that contain the CodeDeploy agent\. Otherwise, an error might occur when the CodeDeploy agent is installed or updated on the instances\. To grant the IAM instance profile access to only some CodeDeploy resource kit buckets in Amazon S3, use the following policy, but remove the lines for buckets you want to prevent access to:
- **Note**  
If you want to use [ IAM authorization](https://docs.aws.amazon.com/IAM/latest/UserGuide/intro-structure.html#intro-structure-authorization) or Amazon Virtual Private Cloud \(VPC\) endpoints with CodeDeploy, you will need to add more permissions\. See [Use CodeDeploy with Amazon Virtual Private Cloud](https://docs.aws.amazon.com/codedeploy/latest/userguide/vpc-endpoints) for more information\.

