---
id: Monitoring
title: Monitoring
created: 1683841041000
updated: 1683841041000
---
# Monitoring

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-sagemaker-developer-guide.git)
{% endhint %}

## Monitoring with CloudWatch

- **Note**  
Amazon CloudWatch supports [high\-resolution custom metrics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/publishingMetrics.html) and its finest resolution is 1 second\. However, the finer the resolution, the shorter the lifespan of the CloudWatch metrics\. For the 1\-second frequency resolution, the CloudWatch metrics are available for 3 hours\. For more information about the resolution and the lifespan of the CloudWatch metrics, see [GetMetricStatistics](https://docs.aws.amazon.com/AmazonCloudWatch/latest/APIReference/API_GetMetricStatistics.html) in the *Amazon CloudWatch API Reference*\.
- **Tip**  
If you want to profile your training job with a finer resolution down to 100\-millisecond \(0\.1 second\) granularity and store the training metrics indefinitely in Amazon S3 for custom analysis at any time, consider using [Amazon SageMaker Debugger](https://docs.aws.amazon.com/sagemaker/latest/dg/train-debugger.html)\. SageMaker Debugger provides built\-in rules to automatically detect common training issues; it detects hardware resource utilization issues \(such as CPU, GPU, and I/O bottlenecks\) and non\-converging model issues \(such as overfit, vanishing gradients, and exploding tensors\)\. SageMaker Debugger also provides visualizations through Studio and its profiling report\. To explore the Debugger visualizations, see [SageMaker Debugger Insights Dashboard Walkthrough](https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-on-studio-insights-walkthrough.htm), [Debugger Profiling Report Walkthrough](https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-profiling-report.html#debugger-profiling-report-walkthrough), and [Analyze Data Using the SMDebug Client Library](https://docs.aws.amazon.com/sagemaker/latest/dg/debugger-analyze-data.html)\.


## Logging with CloudWatch

- **Note**  
1\. The `/aws/sagemaker/NotebookInstances/[LifecycleConfigHook]` log stream is created when you create a notebook instance with a lifecycle configuration\. For more information, see [Customize a Notebook Instance Using a Lifecycle Configuration Script](notebook-lifecycle-config.md)\.  
2\. For Inference Pipelines, if you don't provide container names, the platform uses \*\*container\-1, container\-2\*\*, and so on, corresponding to the order provided in the SageMaker model\.


## Automating with EventBridge

- **Important**  
The following examples may not work for all endpoints\. For a list of features that may exclude your endpoint, see the [Exclusions](deployment-guardrails-exclusions.md) page\.

