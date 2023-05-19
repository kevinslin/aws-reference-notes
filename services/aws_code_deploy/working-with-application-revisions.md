---
id: Working with application revisions
title: Working with application revisions
created: 1683841041000
updated: 1683841041000
---
# Working with application revisions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codedeploy-user-guide.git)
{% endhint %}

## Add an AppSpec File

- **Note**  
 Deployments to Windows Server instances do not support the `runas` element\. If you are deploying to Windows Server instances, do not include it in your AppSpec file\.


## Choose a repository type

- **Note**  
An AWS Lambda deployment works with an Amazon S3 repository only\.


## Push a revision

- **Note**  
CodeDeploy can also be used to deploy revisions that have been pushed to GitHub\. For more information, see your GitHub documentation\.
- **Note**  
 The `push` command bundles application artifacts and an AppSpec file into a revision\. The file format of this revision is a compressed ZIP file\. The command cannot be used with an AWS Lambda or an Amazon ECS deployment because each expects a revision that is a JSON\-formatted or YAML\-formatted AppSpec file\.


## View application revision details

- **Note**  
 References to GitHub apply to deployments to EC2/On\-Premises deployments only\. Revisions for AWS Lambda deployments do not work with GitHub\.


## Register an application revision

- **Note**  
AWS Lambda deployments do not work with GitHub\.

