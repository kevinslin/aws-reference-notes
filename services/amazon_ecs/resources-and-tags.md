---
id: Resources and tags
title: Resources and tags
created: 1683841041000
updated: 1683841041000
---
# Resources and tags

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ecs-developer-guide.git)
{% endhint %}

## Tagging your resources

- **Note**  
If you've turned on reporting, it can take up to 24 hours before the data for the current month is available for viewing\.


## Service quotas

- **Note**  
The default values are the initial quotas set by AWS, which are separate from the actual applied quota value and maximum possible service quota\. For more information, see [Terminology in Service Quotas](https://docs.aws.amazon.com/servicequotas/latest/userguide/intro.html#intro_getting-started) in the *Service Quotas User Guide*\.
- **Note**  
<a name="service-quotas-ecs-note-1"></a>Services configured to use Amazon ECS service discovery have a limit of 1,000 tasks per service\. This is due to the AWS Cloud Map service quota for the number of instances per service\. For more information, see [AWS Cloud Map service quotas](https://docs.aws.amazon.com/general/latest/gr/cloud_map.html) in the *Amazon Web Services General Reference*\.
- **Note**  
<a name="service-quotas-ecs-note-2"></a>In practice, task launch rates are also dependent on other considerations such as container images to be downloaded and unpacked, health checks and other integrations enabled, such as registering tasks with a load balancer\. You might see variations in task launch rates compared with the quotas that are represented here\. These variations are causes by the features that you have enabled for your Amazon ECS services\. For more information, see [speeding up Amazon ECS deployments](https://docs.aws.amazon.com/AmazonECS/latest/bestpracticesguide/deployment.html) in the Amazon ECS Best Practices Guide\.
- **Note**  
Services configured to use Amazon ECS Service Connect have a limit of 1,000 tasks per service\. This is due to the AWS Cloud Map service quota for the number of instances per service\. For more information, see [AWS Cloud Map service quotas](https://docs.aws.amazon.com/general/latest/gr/cloud_map.html) in the *Amazon Web Services General Reference*\.
- **Note**  
The default values are the initial quotas set by AWS, which are separate from the actual applied quota value and maximum possible service quota\. For more information, see [Terminology in Service Quotas](https://docs.aws.amazon.com/servicequotas/latest/userguide/intro.html#intro_getting-started) in the *Service Quotas User Guide*\.
- **Note**  
Fargate additionally enforces Amazon ECS tasks and Amazon EKS pods launch rate limits\. For more information, see [Fargate throttling limits](https://docs.aws.amazon.com/AmazonECS/latest/userguide/throttling.html)\.
- **Note**  
Amazon ECS doesn't support applied quotas\.


## Usage Reports

- **Important**  
The metering data is only viewable for tasks that are launched on or after November 16, 2018\. Tasks that are launched before this date don't show metering data\.
- **Note**  
AWS Cost Management calculates the *Split Cost Allocation Data* with the task CPU and memory usage\. AWS Cost Management can use the task CPU and memory reservation instead of the usage, if the usage is unavailable\. If you see the CUR is using the reservations, check that your container instances meet the prerequisites and the task resource usage metrics appear in CloudWatch\.

