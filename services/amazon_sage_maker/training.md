---
id: Training
title: Training
created: 1683841041000
updated: 1683841041000
---
# Training

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-sagemaker-developer-guide.git)
{% endhint %}

## Distributed Training

- **Tip**  
Adjust your hyperparameters to ensure that your model trains to a satisfying convergence as you increase its batch size\.
- **Note**  
The ml instance types used by SageMaker training have the same number of GPUs as the corresponding p3 instance types\. For example, `ml.p3.8xlarge` has the same number of GPUs as `p3.8xlarge` \- 4\.


## Training Compiler

- **Tip**  
SageMaker Training Compiler only compiles DL models for training on [supported GPU instances](https://docs.aws.amazon.com/sagemaker/latest/dg/training-compiler-support.html#training-compiler-supported-instance-types) managed by SageMaker\. To compile your model for inference and deploy it to run anywhere in the cloud and at the edge, use [SageMaker Neo compiler](https://docs.aws.amazon.com/sagemaker/latest/dg/neo.html)\.


## Access Training Data

- **Tip**  
To learn more about how to configure Amazon FSx for Lustre or Amazon EFS with your VPC configuration using the SageMaker Python SDK estimators, see [Use File Systems as Training Inputs](https://sagemaker.readthedocs.io/en/stable/overview.html?highlight=VPC#use-file-systems-as-training-inputs) in the *SageMaker Python SDK documentation*\.
- **Tip**  
The data input mode integrations with Amazon S3, Amazon EFS, and FSx for Lustre are recommended ways to optimally configure data source for the best practices\. You can strategically improve data loading performance using the SageMaker managed storage options and input modes, but it's not strictly constrained\. You can write your own data reading logic directly in your training container\. For example, you can set to read from a different data source, write your own S3 data loader class, or use third\-party frameworks' data loading functions within your training script\. However, you must make sure that you specify the right paths that SageMaker can recognize\.
- **Tip**  
If you use a custom training container, make sure you install the [SageMaker training toolkit](https://github.com/aws/sagemaker-training-toolkit) that helps set up the environment for SageMaker training jobs\. Otherwise, you must specify the environment variables explicitly in your Dockerfile\. For more information, see [Create a container with your own algorithms and models](https://docs.aws.amazon.com/sagemaker/latest/dg/docker-containers-create.html)\.
- **Tip**  
When you specify `directory_path`, make sure that you provide the Amazon FSx file system path starting with `MountName`\.
- **Tip**  
When you specify `DirectoryPath`, make sure that you provide the Amazon FSx file system path starting with `MountName`\.
- **Tip**  
To learn more, see [Choose the best data source for your Amazon SageMaker training job](http://aws.amazon.com/blogs/machine-learning/choose-the-best-data-source-for-your-amazon-sagemaker-training-job/)\. This AWS machine learning blog further discusses case studies and performance benchmark of data sources and input modes\.


## Heterogeneous Cluster Training

- **Note**  
This feature is available in the SageMaker Python SDK v2\.98\.0 and later\.
- **Note**  
This feature is available through the SageMaker [PyTorch](https://sagemaker.readthedocs.io/en/stable/frameworks/pytorch/sagemaker.pytorch.html) and [TensorFlow](https://sagemaker.readthedocs.io/en/stable/frameworks/tensorflow/sagemaker.tensorflow.html#tensorflow-estimator) framework estimator classes\. Supported frameworks are PyTorch v1\.10 or later and TensorFlow v2\.6 or later\.
- **Note**  
The `instance_type` and `instance_count` argument pair and the `instance_groups` argument of the SageMaker estimator class are mutually exclusive\. For homogeneous cluster training, use the `instance_type` and `instance_count` argument pair\. For heterogeneous cluster training, use `instance_groups`\.
**Note**  
To find a complete list of available framework containers, framework versions, and Python versions, see [SageMaker Framework Containers](https://github.com/aws/deep-learning-containers/blob/master/available_images.md#sagemaker-framework-containers-sm-support-only) in the AWS Deep Learning Container GitHub repository\.
- **Note**  
Currently, only one instance group of a heterogeneous cluster can be specified to the distribution configuration\.
- **Note**  
When using the SageMaker data parallel library, make sure the instance group consists of the [supported instance types by the library](https://docs.aws.amazon.com/sagemaker/latest/dg/distributed-data-parallel-support.html#distributed-data-parallel-supported-instance-types)\.


## Incremental Training

- **Important**  
Only three built\-in algorithms currently support incremental training: [Object Detection \- MXNet](object-detection.md), [Image Classification \- MXNet](image-classification.md), and [Semantic Segmentation Algorithm](semantic-segmentation.md)\.
- **Note**  
In this example we used the original datasets in the incremental training, however you can use different datasets, such as ones that contain newly added samples\. Upload the new datasets to S3 and make adjustments to the `data_channels` variable used to train the new model\.


## Managed Spot Training

- **Note**  
Unless your training job will complete quickly, we recommend you use checkpointing with managed spot training\. SageMaker built\-in algorithms and marketplace algorithms that do not checkpoint are currently limited to a `MaxWaitTimeInSeconds` of 3600 seconds \(60 minutes\)\.


## Managed Warm Pools

- **Important**  
SageMaker Managed Warm Pools are a billable resource\. For more information, see [Billing](#train-warm-pools-billing)\.
- **Note**  
All warm pool instance usage counts toward your SageMaker training resource limit\. Increasing your warm pool resource limit does not increase your instance limit, but allocates a subset of your resource limit to warm pool training\.
- **Note**  
This feature is available in the SageMaker [Python SDK v2\.110\.0](https://pypi.org/project/sagemaker/2.110.0/) and later\.
- **Note**  
Training job names have date/time suffixes\. The example training job names `my-training-job-1` and `my-training-job-2` should be replaced with actual training job names\. You can use the `estimator.latest_training_job.job_name` command to fetch the actual training job name\.


## Monitor and Analyze Using CloudWatch Metrics

- **Note**  
Amazon CloudWatch supports [high\-resolution custom metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/publishingMetrics.html), and its finest resolution is 1 second\. However, the finer the resolution, the shorter the lifespan of the CloudWatch metrics\. For the 1\-second frequency resolution, the CloudWatch metrics are available for 3 hours\. For more information about the resolution and the lifespan of the CloudWatch metrics, see [GetMetricStatistics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/APIReference/API_GetMetricStatistics.html) in the *Amazon CloudWatch API Reference*\.
- **Tip**  
If you want to profile your training job with a finer resolution down to 100\-millisecond \(0\.1 second\) granularity and store the training metrics indefinitely in Amazon S3 for custom analysis at any time, consider using [Amazon SageMaker Debugger](https://docs.aws.amazon.com/sagemaker/latest/dg/train-debugger.html)\. SageMaker Debugger provides built\-in rules to automatically detect common training issues; it detects hardware resource utilization issues \(such as CPU, GPU, and I/O bottlenecks\) and non\-converging model issues \(such as overfit, vanishing gradients, and exploding tensors\)\. SageMaker Debugger also provides visualizations through Studio and its profiling report\. To explore the Debugger visualizations, see [SageMaker Debugger Insights Dashboard Walkthrough](https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-on-studio-insights-walkthrough.htm), [Debugger Profiling Report Walkthrough](https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-profiling-report.html#debugger-profiling-report-walkthrough), and [Analyze Data Using the SMDebug Client Library](https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-analyze-data.html)\.


## Use Augmented Manifest Files

- **Tip**  
To create an augmented manifest file, use Amazon SageMaker Ground Truth and create a labeling job\. For more information about the output from a labeling job, see [Output Data](sms-data-output.md)\.

