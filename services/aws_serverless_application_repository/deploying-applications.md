---
id: Deploying Applications
title: Deploying Applications
created: 1683841041000
updated: 1683841041000
---
# Deploying Applications

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-serverlessrepo-developer-guide.git)
{% endhint %}

## Application Deployment Permissions

- **Important**  
Applications that contain nested applications inherit the nested applications' sharing restrictions\. For example, suppose an application is publicly shared, but it contains a nested application that's only privately shared with the AWS account that created the parent application\. In this case, if your AWS account doesn't have permission to deploy the nested application, then you aren't able to deploy the parent application\. For more information about nested applications, see [Nested Applications](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-template-nested-applications.html) in the *AWS Serverless Application Model Developer Guide*\.

