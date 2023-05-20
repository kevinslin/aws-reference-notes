---
id: Working with Projects
title: Working with Projects
created: 1683841041000
updated: 1683841041000
---
# Working with Projects

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codestar-user-guide.git)
{% endhint %}

## Create a Project

- **Note**  
You must complete the steps in [Setting Up AWS CodeStar](setting-up.md) before you can complete the procedures in this topic\.
- **Important**  
Make sure you configure the preferred AWS Region in the AWS CLI\. Your project is created in the AWS Region configured in the AWS CLI\.


## Shift Traffic for an AWS Lambda Project

- **Note**  
Complete these steps only if you created your AWS CodeStar project before December 12, 2018\.


## Transition your AWS CodeStar Project to Production

- **Note**  
It can be helpful to create or view a similar project using one of the AWS CodeStar quick starts first and use that as a template for your own project to make sure you include the resources and policies you need\.


## Delete a Project

- **Important**  
Deleting a project in AWS CodeStar cannot be undone\. By default all AWS resources for the project are deleted in your AWS account, including:  
The CodeCommit repository for the project along with anything stored in that repository\.
The AWS CodeStar project roles and the associated IAM policies configured for the project and its resources\.
Any Amazon EC2 instances created for the project\.
The deployment application and associated resources, such as:  
A CodeDeploy application and associated deployment groups\.
An AWS Lambda function and associated API Gateway APIs\.
An AWS Elastic Beanstalk application and associated environment\.
The continuous deployment pipeline for the project in CodePipeline\.
The AWS CloudFormation stacks associated with the project\.
Any AWS Cloud9 development environments created with the AWS CodeStar console\. All uncommitted code changes in the environments are lost\. 
To delete all project resources along with the project, select the **Delete resources** check box\. If you clear this option, the project is deleted in AWS CodeStar, and the project roles that enabled access to those resources are deleted in IAM, but all other resources are retained\. You might continue to incur charges for these resources in AWS\. If you decide you no longer want one or more of these resources, you must manually delete them\. For more information, see [Project deletion: An AWS CodeStar project was deleted, but resources still exist](troubleshooting.md#troubleshooting-pd1)\.  
If you decide to keep resources when you delete a project, as a best practice, copy the list of resources from the project details page\. This way, you have a record of all resources that you have kept, even though the project no longer exists\.

