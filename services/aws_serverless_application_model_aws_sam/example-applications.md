---
id: Example applications
title: Example applications
created: 1683841041000
updated: 1683841041000
---
# Example applications

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-sam-developer-guide.git)
{% endhint %}

## Process Amazon S3 events

- **Note**  
With this example application, you perform steps in a slightly different order than in previous examples\. The reason for this is that this example requires that AWS resources are created and IAM permissions are configured *before* you can test the Lambda function locally\. We're going to leverage AWS CloudFormation to create the resources and configure the permissions for you\. Otherwise, you would need to do this manually before you can test the Lambda function locally\.  
Because this example is more complicated, be sure that you're familiar with installing the previous example applications before executing this one\.

