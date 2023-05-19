---
id: Reference
title: Reference
created: 1683841041000
updated: 1683841041000
---
# Reference

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codedeploy-user-guide.git)
{% endhint %}

## AppSpec file reference

- **Note**  
The AppSpec file for an EC2/On\-Premises deployment must be named `appspec.yml` or `appspec.yaml`, unless you are performing a local deployment\. For more information, see [Create a local deployment](deployments-local.md#deployments-local-deploy)\.
- **Note**  
The tar and compressed tar archive file formats \(\.tar and \.tar\.gz\) are not supported for Windows Server instances\.


## AWS CloudFormation template reference

- **Note**  
AWS CloudFormation hooks are part of the AWS CloudFormation components for AWS and are different from CodeDeploy lifecycle event hooks\.


## Resource kit reference

- **Note**  
 To access the Amazon S3 bucket in the Asia Pacific \(Hong Kong\) Region, you must enable the region in your AWS account\. For more information, see [Managing AWS Regions](https://docs.aws.amazon.com/general/latest/gr/rande-manage.html#rande-manage-enable)\.
- **Note**  
The files in each bucket are designed to work with resources in the corresponding region\.
+
- **Note**  
Be sure to use the period \(`.`\) near the end\. This downloads the file to your current directory\.


## Limits

- **Note**  
You can [request a limit increase](https://console.aws.amazon.com/support/home#/case/create%3FissueType=service-limit-increase) for the CodeDeploy limits listed in [AWS service limits](https://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_codedeploy) in the *Amazon Web Services General Reference* \. You cannot increase the limit on the number of hours a deployment can run\.

