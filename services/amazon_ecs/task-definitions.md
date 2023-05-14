---
id: Task definitions
title: Task definitions
created: 1683841041000
updated: 1683841041000
---
# Task definitions
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ecs-developer-guide.git)
{% endhint %}
## Task definition parameters

- **Note**  
Task\-level CPU and memory parameters are ignored for Windows containers\. We recommend specifying container\-level resources for Windows containers\.
- **Note**  
Starting April 15, 2023, AWS will not onboard new customers to Amazon Elastic Inference \(EI\), and will help current customers migrate their workloads to options that offer better price and performance\. After April 15, 2023, new customers will not be able to launch instances with Amazon EI accelerators in Amazon SageMaker, Amazon ECS, or Amazon EC2\. However, customers who have used Amazon EI at least once during the past 30\-day period are considered current customers and will be able to continue using the service\.
- **Important**  
Don't add personally identifiable information or other confidential or sensitive information in tags\. Tags are accessible to many AWS services, including billing\. Tags aren't intended to be used for private or sensitive data\.
- **Note**  
This parameter is not supported for Windows containers or tasks using the Fargate launch type\.
- **Note**  
This parameter is not supported for Windows containers or tasks using the Fargate launch type\.


## Using the awslogs log driver

- **Note**  
The type of information that is logged by the containers in your task depends mostly on their `ENTRYPOINT` command\. By default, the logs that are captured show the command output that you typically might see in an interactive terminal if you ran the container locally, which are the `STDOUT` and `STDERR` I/O streams\. The `awslogs` log driver simply passes these logs from Docker to CloudWatch Logs\. For more information about how Docker logs are processed, including alternative ways to capture different file data or streams, see [View logs for a container or service](https://docs.docker.com/config/containers/logging/) in the Docker documentation\.
- **Note**  
If you aren't using the Amazon ECS optimized AMI \(with at least version 1\.9\.0\-1 of the `ecs-init` package\) for your container instances, you also need to specify that the `awslogs` logging driver is available on the container instance when you start the agent by using the following environment variable in your docker run statement or environment variable file\. For more information, see [Installing the Amazon ECS container agent](ecs-agent-install.md)\.
- **Note**  
To use the `awslogs-create-group` option to have your log group created, your task execution IAM role policy or EC2 instance role policy must include the `logs:CreateLogGroup` permission\.


## Private registry authentication for tasks

- **Important**  
If your task definition references an image that's stored in Amazon ECR, this topic doesn't apply\. For more information, see [Using Amazon ECR Images with Amazon ECS](https://docs.aws.amazon.com/AmazonECR/latest/userguide/ECR_on_ECS.html) in the *Amazon Elastic Container Registry User Guide*\.
- **Note**  
When using the Amazon ECS API, AWS CLI, or AWS SDK, if the secret exists in the same AWS Region as the task that you're launching then you can use either the full ARN or name of the secret\. If the secret exists in a different account, the full ARN of the secret must be specified\. When using the AWS Management Console, the full ARN of the secret must be specified always\.
- **Note**  
Another method of enabling private registry authentication uses Amazon ECS container agent environment variables to authenticate to private registries\. This method is only supported for tasks hosted on Amazon EC2 instances\. For more information, see [Private registry authentication for container instances](private-auth-container-instances.md)\.


## Passing environment variables

- **Important**  
We recommend storing your sensitive data in either AWS Secrets Manager secrets or AWS Systems Manager Parameter Store parameters\. For more information, see [Passing sensitive data to a container](specifying-sensitive-data.md)\.  
Environment variables specified in the task definition are readable by all users and roles that are allowed the `DescribeTaskDefinition` action for the task definition\.  
Environment variable files are objects in Amazon S3 and all Amazon S3 security considerations apply\. See the below section [Required IAM permissions](#taskdef-envfiles-iam)\.

