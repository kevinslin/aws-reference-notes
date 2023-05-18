---
id: 'Autopilot: Automated ML'
title: 'Autopilot: Automated ML'
created: 1683841041000
updated: 1683841041000
---
# Autopilot: Automated ML

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-sagemaker-developer-guide.git)
{% endhint %}

## Create an Autopilot experiment

- **Note**  
To avoid incurring unnecessary charges: If you deploy a model that is no longer needed, delete the endpoints and resources that were created during that deployment\. Information about pricing instances by Region is available at [Amazon SageMaker Pricing](http://aws.amazon.com/sagemaker/pricing/)\.
- **Note**  
The list of columns provided as features cannot include the target column\.
- **Note**  
In some cases, Autopilot is unable to infer the `ProblemType` with high enough confidence, in which case you must provide the value for the job to succeed\.


## Training modes and algorithm support

- **Note**  
For optimal runtime and performance, use ensemble training mode for datasets that are smaller than 100 MB\.
- **Note**  
You don't need to specify an algorithm to use for your machine learning problem\. Autopilot automatically selects the appropriate algorithm to train\.


## Metrics and validation

- **Note**  
In HPO mode, you can see the training and validation metrics from each fold in your `/aws/sagemaker/TrainingJobs` CloudWatch Logs\. For more information about CloudWatch Logs, see [Log Amazon SageMaker Events with Amazon CloudWatch](logging-cloudwatch.md)\.


## Model Deployment and Prediction

- **Note**  
To avoid incurring unnecessary charges: After the endpoints and resources that were created from model deployment are longer needed, you can delete them\. For information about pricing of instances by Region, see [Amazon SageMaker Pricing](http://aws.amazon.com/sagemaker/pricing/)\.


## Notebooks generated

- **Note**  
When you run the notebooks in your default instance, you incur baseline costs\. However, when you run HPO jobs from the candidate notebook, these jobs use additional compute resources that incur additional costs\.


## Quotas

- **Note**  
The resource quotas documented in the following sections are valid for versions of Amazon SageMaker Studio 3\.22\.2 and higher\. For information on updating your version of SageMaker Studio, see [Shut Down and Update SageMaker Studio and Studio Apps](studio-tasks-update.md)\.
- **Note**  
\*This 2 GB size limit is for a single compressed Parquet file\. You can provide a Parquet dataset that includes multiple compressed Parquet files\. After the files are decompressed, they may each expand to a larger size\.  
\*\*Autopilot automatically subsamples input datasets that are larger than the target dataset size while accounting for class imbalance and preserving rare class labels\.

