---
id: Sample projects for Step Functions
title: Sample projects for Step Functions
created: 1683841041000
updated: 1683841041000
---
# Sample projects for Step Functions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## Poll for Job Status (Lambda, AWS Batch)

- **Note**  
You can also implement this pattern without using a Lambda function\. For information about controlling AWS Batch directly, see [Using AWS Step Functions with other services](concepts-service-integrations.md)\.
- **Note**  
`wait_time` instructs the `Wait` state to loop every 60 seconds\.


## Task Timer (Lambda, Amazon SNS)

- **Note**  
This sample project implements an AWS Lambda function to send an Amazon Simple Notification Service \(Amazon SNS\) notification\. You can also send an Amazon SNS notification directly from the Amazon States Language\. See [Using AWS Step Functions with other services](concepts-service-integrations.md)\.


## Manage an Amazon EMR Job

- **Important**  
Amazon EMR does not have a free pricing tier\. Running the sample project will incur costs\. You can find pricing information on the [Amazon EMR pricing](http://aws.amazon.com/emr/pricing/) page\. The availability of Amazon EMR service integration is subject to the availability of Amazon EMR APIs\. Because of this, this sample project might not work correctly in some AWS Regions\. See the [Amazon EMR](https://docs.aws.amazon.com/govcloud-us/latest/UserGuide/govcloud-emr.html) documentation for limitations in special Regions\.


## Dynamically process data with a Map state

- **Note**  
Queues in Amazon SNS are eventually consistent\. For best results, wait a few minutes between populating your queue and running an execution of your state machine\.


## Train a Machine Learning Model

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [SageMaker Pricing](https://aws.amazon.com/sagemaker/pricing/)\.


## Tune a Machine Learning Model

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [SageMaker Pricing](https://aws.amazon.com/sagemaker/pricing/)\.


## Preprocess data and train a machine learning model

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [SageMaker Pricing](https://aws.amazon.com/sagemaker/pricing/)\.


## Lambda orchestration example

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the free tier, see [Pricing](http://aws.amazon.com/step-functions/pricing)\.


## Start an Athena query

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [Athena Pricing](https://aws.amazon.com/athena/pricing/)\.


## Manage an Amazon EKS cluster

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [Amazon EKS Pricing](https://aws.amazon.com/eks/pricing/)\.


## Call a microservice with API Gateway

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [Pricing](http://aws.amazon.com/step-functions/pricing)\.


## Send a custom event to EventBridge

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [EventBridge Pricing](https://aws.amazon.com/eventbridge/pricing/)\.


## Invoke Synchronous Express Workflows

- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [Step Functions Pricing](https://aws.amazon.com/step-functions/pricing/)\.


## Run ETL/ELT workflows using Amazon Redshift

- **Note**  
 You can modify the ETL logic to receive data from other sources such as Amazon S3, which can use the [COPY](https://docs.aws.amazon.com/redshift/latest/dg/r_COPY.html) command to copy data from Amazon S3 to an Amazon Redshift table\.
- **Note**  
This sample project may incur charges\.  
For new AWS users, a free usage tier is available\. On this tier, services are free below a certain level of usage\. For more information about AWS costs and the Free Tier, see [AWS Step Functions pricing](https://aws.amazon.com/step-functions/pricing/)\.

