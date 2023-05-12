---
id: Working with other services
title: Working with other services
created: 1683841041000
updated: 1683841041000
---
# Working with other services
## Amazon Elastic Container Service on AWS Outposts

- **Note**  
In order to avoid delays caused by pulling container images from Amazon ECR in the Region, use image caches\. To do this, each time a task is run, configure the Amazon ECS agent to default to using the cached image on the instance itself by setting `ECS_IMAGE_PULL_BEHAVIOR` to `prefer-cached`\.
- **Note**  
This command is also used when adding additional instances to the cluster\. Any containers deployed in the cluster will be placed on that specific AWS Outposts\.


## Use App Mesh with Amazon ECS

- **Note**  
This feature is not available for Window containers on Fargate\.


## AWS Deep Learning Containers on Amazon ECS

- **Note**  
Starting April 15, 2023, AWS will not onboard new customers to Amazon Elastic Inference \(EI\), and will help current customers migrate their workloads to options that offer better price and performance\. After April 15, 2023, new customers will not be able to launch instances with Amazon EI accelerators in Amazon SageMaker, Amazon ECS, or Amazon EC2\. However, customers who have used Amazon EI at least once during the past 30\-day period are considered current customers and will be able to continue using the service\.
- **Important**  
Your Amazon ECS container instances require at least version `1.30.0` of the container agent\. For information about checking your agent version and updating to the latest version, see [Updating the Amazon ECS container agent](ecs-agent-update.md)\.

