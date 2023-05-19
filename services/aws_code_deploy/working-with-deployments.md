---
id: Working with deployments
title: Working with deployments
created: 1683841041000
updated: 1683841041000
---
# Working with deployments

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codedeploy-user-guide.git)
{% endhint %}

## View deployment details

- **Note**  
You can view EC2/On\-Premises deployment logs on your instances in the following locations:  
Amazon Linux, RHEL, and Ubuntu Server: `/opt/codedeploy-agent/deployment-root/deployment-logs/codedeploy-agent-deployments.log`
Windows Server: C:\\ProgramData\\Amazon\\CodeDeploy<DEPLOYMENT\-GROUP\-ID><DEPLOYMENT\-ID>\\logs\\scripts\.log
For more information, see [Analyzing log files to investigate deployment failures on instances](troubleshooting-ec2-instances.md#troubleshooting-deploy-failures)\.


## View deployment log data

- **Note**  
 Logs are not supported for AWS Lambda or Amazon ECS deployments\. They can be created for EC2/On\-Premises deployments only\.


## Stop a deployment

- **Note**  
If your deployment is a blue/green deployment through AWS CloudFormation, you cannot perform this task in the CodeDeploy console\. Go to the AWS CloudFormation console to perform this task\.


## Redeploy and roll back a deployment

- **Note**  
You can use Amazon Simple Notification Service to receive a notification whenever a deployment is rolled back automatically\. For information, see [Monitoring deployments with Amazon SNS event notifications](monitoring-sns-event-notifications.md)\.
- **Note**  
If you remove an instance from a deployment group, CodeDeploy does not uninstall anything that might have already been installed on that instance\.


## Deploy an application in a different AWS account

- **Important**  
As you create the cross\-account IAM role, make a note of the details you will need to gain access to the production account\.  
To use the AWS Management Console to switch roles, you will need to supply either of the following:  
A URL for accessing the production account with the assumed role's credentials\. You will find the URL on the **Review** page, which is displayed at the end of the cross\-account role creation process\.
The name of the cross\-account role and either the account ID number or alias\. 
To use the AWS CLI to switch roles, you will need to supply the following:  
The ARN of the cross\-account role you will assume\.


## Validate a deployment package on a local machine

- **Note**  
 The codedeploy\-local command is installed in the following locations:   
 On Amazon Linux, RHEL, or Ubuntu Server: `/opt/codedeploy-agent/bin`\. 
 On Windows Server: `C:\ProgramData\Amazon\CodeDeploy\bin`\.

