---
id: Deploy Models for Inference
title: Deploy Models for Inference
created: 1683841041000
updated: 1683841041000
---
# Deploy Models for Inference

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-sagemaker-developer-guide.git)
{% endhint %}

## Asynchronous inference

- **Note**  
The presence of an asynchronous inference configuration \(`AsyncInferenceConfig`\) object in the endpoint configuration implies that the endpoint can only receive asynchronous invocations\.


## Batch Transform

- **Note**  
SageMaker processes each input file separately\. It doesn't combine mini\-batches from different input files to comply with the [https://docs.aws.amazon.com/sagemaker/latest/APIReference/API_CreateTransformJob.html#SageMaker-CreateTransformJob-request-MaxPayloadInMB               ](https://docs.aws.amazon.com/sagemaker/latest/APIReference/API_CreateTransformJob.html#SageMaker-CreateTransformJob-request-MaxPayloadInMB               ) limit\.


## Deployment guardrails

- **Note**  
Deployment guardrails only apply to [Asynchronous inference](async-inference.md) and [Real\-time inference](realtime-endpoints.md) endpoint types\.


## Container SSM access

- **Note**  
 You cannot connect to 1P algorithm containers or containers of models obtained from SageMaker MarketPlace with SSM\. However you can connect to deep learning containers \(DLCs\) provided by AWS or any custom container that you own\. 
 If you have enabled network isolation for a model container that prevents it from making outbound network calls, you cannot start an SSM session for that container\. 
 You can only access one container from one SSM session\. To access another container, even if it is behind the same endpoint, start a new SSM session with the target ID of thath endpoint\.


## Best practices to minimize interruptions during GPU driver upgrades

- **Important**  
The CUDA Compatibility Package is not backwards compatible so it needs to be disabled if the driver version on the instance is greater than the CUDA Compatibility Package version\.

