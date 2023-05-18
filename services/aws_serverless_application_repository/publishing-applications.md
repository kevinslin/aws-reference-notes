---
id: Publishing Applications
title: Publishing Applications
created: 1683841041000
updated: 1683841041000
---
# Publishing Applications

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-serverlessrepo-developer-guide.git)
{% endhint %}

## Using AWS SAM with the AWS Serverless Application Repository

- **Important**  
If your application template contains one of the following custom IAM roles or resource policies, your application doesn't show up in search results by default\. Also, customers need to acknowledge the application's custom IAM roles or resource policies before they can deploy the application\. For more information, see [ Acknowledging Application Capabilities](acknowledging-application-capabilities.md)\.   
The list of resources that this applies to are:  
**IAM roles: **[AWS::IAM::Group](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-group.html), [AWS::IAM::InstanceProfile](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-instanceprofile.html), [AWS::IAM::Policy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-policy.html), and [AWS::IAM::Role](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-role.html)\.
**Resource policies: ** [AWS::Lambda::LayerVersionPermission](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-lambda-layerversionpermission.html), [AWS::Lambda::Permission](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-lambda-permission.html), [AWS::Events::EventBusPolicy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-events-eventbuspolicy.html), [AWS::IAM:Policy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-policy.html), [AWS::ApplicationAutoScaling::ScalingPolicy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-applicationautoscaling-scalingpolicy.html), [AWS::S3::BucketPolicy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-s3-policy.html), [AWS::SQS::QueuePolicy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-sqs-policy.html), and [AWS::SNS:TopicPolicy](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-sns-policy.html)\.
If your application contains the [AWS::Serverless::Application](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-template.html#serverless-sam-template-application) resource, customers need to acknowledge that the application contains a **nested application** before they can deploy the application\. For more information about nested applications, see [Nested Applications](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-template-nested-applications.html) in the *AWS Serverless Application Model Developer Guide*\. For more information about acknowledging capabilities, see [Acknowledging Application Capabilities](acknowledging-application-capabilities.md)\.


## How to Publish Applications

- **Important**  
The information that you enter when you publish an application isn't encrypted\. This information includes data such as the author name\. If you have personally identifiable information that you don't want to be stored or made public, we recommend that you don't enter this information when publishing your application\.
- **Note**  
In order to share an application publicly, it must have both the `SemanticVersion` and `LicenseUrl` properties set\.


## Verified Author Badge

- **Note**  
The verified author badge is displayed for all applications that match both the AWS account and author name\. Because AWS accounts can have multiple authors, badges aren't be displayed on applications that have a different author name\. To have author badges displayed on applications with different author names, you must submit another request for that author\.

