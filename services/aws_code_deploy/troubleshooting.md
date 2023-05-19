---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codedeploy-user-guide.git)
{% endhint %}

## General troubleshooting issues

- **Important**  
To use services in the China \(Beijing\) Region or China \(Ningxia\) Region, you must have an account and credentials for those regions\. Accounts and credentials for other AWS regions do not work for the Beijing and Ningxia Regions, and vice versa\.  
Information about some resources for the China Regions, such as CodeDeploy Resource Kit bucket names and CodeDeploy agent installation procedures, are not included in this edition of the *CodeDeploy User Guide*\.  
For more information:  
[CodeDeploy](http://docs.amazonaws.cn/en_us/aws/latest/userguide/codedeploy.html) in *[Getting Started with AWS in the China \(Beijing\) Region](http://docs.amazonaws.cn/en_us/aws/latest/userguide/introduction.html) *
*CodeDeploy User Guide for the China Regions* \([English version](http://docs.amazonaws.cn/en_us/codedeploy/latest/userguide/welcome.html) \| [Chinese version](http://docs.amazonaws.cn/codedeploy/latest/userguide/welcome.html)\)


## Troubleshoot EC2/On-Premises deployment issues

- **Note**  
The causes of many deployment failures can be identified by reviewing the log files created during the deployment process\. For simplicity, we recommend using Amazon CloudWatch Logs to centrally monitor log files instead of viewing them instance by instance\. For information, see [View CodeDeploy Logs in CloudWatch Logs Console](http://aws.amazon.com/blogs/devops/view-aws-codedeploy-logs-in-amazon-cloudwatch-console/)\.
- **Note**  
On Amazon Linux, RHEL, and Ubuntu Server instances, the cleanup file is located in `/opt/codedeploy-agent/deployment-root/deployment-instructions/`\. On Windows Server instances, the location is `C:\ProgramData\Amazon\CodeDeploy\deployment-instructions\`\.


## Troubleshoot instance issues

- **Note**  
If you tag an instance and immediately use CodeDeploy to deploy an application to it, the instance might not be included in the deployment\. This is because it can take several minutes before CodeDeploy can read the tags\. We recommend that you wait at least five minutes between the time you tag an instance and attempt to deploy to it\.


## Troubleshoot Amazon EC2 Auto Scaling issues

- **Note**  
After you confirm that deployments are successful, delete the instance you created to avoid ongoing charges to your AWS account\.
- **Note**  
The default timeout for a script in a lifecycle event is 30 minutes\. You can change the timeout to a different value in the AppSpec file\. For more information, see [Add an AppSpec file for an EC2/On\-Premises deployment](application-revisions-appspec-file.md#add-appspec-file-server)\.
- **Note**  
If you detach an Auto Scaling group from a CodeDeploy deployment group, any in\-progress deployments to the Auto Scaling group may fail, and new EC2 instances that are scaled out by the Auto Scaling group will not receive your application revisions from CodeDeploy\. To get Auto Scaling working again with CodeDeploy, you'll need to re\-attach the Auto Scaling group to the deployment group and call a new `CreateDeployment` to start a fleet\-wide deployment\.

