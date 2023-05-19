---
id: AWS Toolkit
title: AWS Toolkit
created: 1683841041000
updated: 1683841041000
---
# AWS Toolkit

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## Navigating and configuring

- **Note**  
If you can't see the option to view the **AWS Explorer** window in the integrated development environment \(IDE\), verify that you enabled the AWS Toolkit\. Then, after you verify it's enabled, try again\. For more information, see [Enabling AWS Toolkit](toolkit-welcome.md#access-toolkit)\.
- **Note**  
You can also hide selected AWS Regions in the **AWS Explorer window** using the following options:  
Open the context \(right\-click\) menu for the Region and choose **Hide region from the Explorer**\.
In the AWS Toolkit menu, choose **Hide region from the Explorer** and select a Region to hide\.


## API Gateway

- **Important**  
Calling API methods using the AWS Toolkit might result in changes to resources that can't be undone\. For example, if you call a `POST` method, the API's resources are updated if the call is successful\.


## AWS App Runner

- **Note**  
The **AWSServiceRoleForAppRunner** service\-linked role allows AWS App Runner to complete the following tasks:  
Push logs to Amazon CloudWatch Logs log groups\.
Create Amazon CloudWatch Events rules to subscribe to Amazon Elastic Container Registry \(Amazon ECR\) image push\.
You don't need to manually create the service\-linked role\. When you create an AWS App Runner in the AWS Management Console or by using API operations that are called by AWS Toolkit, AWS App Runner creates this service\-linked role for you\.
- **Note**  
You can also obtain the URI for a private Amazon ECR repository directly from **AWS Explorer** in the AWS Toolkit:  
Open **AWS Explorer** and expand the **ECR** node to view the list of repositories for that AWS Region\.
Open the context \(right\-click\) menu for a repository and choose **Copy Repository URI** to copy the link to your clipboard\.
- **Important**  
To create GitHub connections, you must use the App Runner console \([https://console\.aws\.amazon\.com/apprunner](https://console.aws.amazon.com/apprunner)\) to create a connection that links GitHub to AWS\. You can select the connections that are available on the **GitHub connections** page when configuring your service instance with the AWS Toolkit's command pane\.  
For more information, see [Managing App Runner connections](https://docs.aws.amazon.com/apprunner/latest/dg/manage-connections.html) in the *AWS App Runner Developer Guide*\.


## AWS Lambda functions

- **Important**  
If you want to build a Lambda application that uses the resources that are provided by the Serverless Application Model \(SAM\), see [Working with AWS serverless applications using the AWS Toolkit](serverless-apps-toolkit.md)\.
- **Note**  
Suppose that you have already created Lambda functions by using the AWS Management Console or in some other way\. You can invoke them from the AWS Toolkit\. To create a new function with AWS Toolkit that you can deploy to AWS Lambda, you must first [create a serverless application](serverless-apps-toolkit.md#sam-create)\.
- **Important**  
Calling API methods using the AWS Toolkit might result in changes to resources that can't be undone\. For example, if you call a `POST` method, the API's resources are updated if the call is successful\.


## AWS Serverless Application

- **Note**  
In this example, we're debugging an application that uses JavaScript\. But you can use debugging features available in the AWS Toolkit with the following languages and runtimes:  
JavaScript – Node\.js 10\.*x*, 12\.*x*, 14\.*x*
Python – 3\.7, 3\.8, 3\.9 \(Python 2\.7 and 3\.6 serverless applications can be run but not debugged by the AWS Toolkit\.\)
Your language choice also affects how context\-aware links indicate eligible Lambda handlers\. For more information, see [Running and debugging serverless functions directly from code](#run-debug-no-template)\.
- **Note**  
API Gateway supports two types of APIs\. They are REST and HTTP APIs\. However, the API Gateway feature with the AWS Toolkit only supports REST APIs\. Sometimes HTTP APIs are called "API Gateway V2 APIs\."


## AWS Systems Manager

- **Note**  
When you first create a local automation document, it doesn't automatically appear in AWS\. Before you can run it, you must publish it to AWS\.
- **Important**  
Deleting is a destructive action that can't be undone\.
Deleting an automation document that has already been started doesn't delete the AWS resources that were created or modified when it was run\.
Deleting is permitted only if you own the document\.
- **Important**  
Running an automation document can create new resources in AWS and can incur billing costs\. We strongly recommend that you understand what your automation document will create in your account before you run it\.


## AWS IoT

- **Note**  
Each of these status\-changing actions is available if you select a certificate that is attached to a thing while displayed in the **Things** subsection\.<a name="cert-attach-policy"></a>
- **Note**  
Named policies are versioned so that you can roll them back\. In the AWS Explorer, your IoT polices are listed under the **Policies** subsection in the AWS IoT service\. You can view policy versions by expanding a policy\. The default version is denoted by an asterisk \(\*\)\.

