---
id: Augmented AI
title: Augmented AI
created: 1683841041000
updated: 1683841041000
---
# Augmented AI

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-sagemaker-developer-guide.git)
{% endhint %}

## Get Started with Amazon Augmented AI

- **Note**  
AWS Region availability may differ when you use Augmented AI with other AWS services, such as Amazon Textract\. Create Augmented AI resources in the same AWS Region that you use to interact with those AWS services\. For AWS Region availability for all services, see the [Region Table](http://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/)\.


## Create a Human Review Workflow

- **Important**  
Human loop activation conditions, which initiate the human loop—for example, confidence thresholds—aren't available for Amazon A2I custom task types\. When using the console to create a flow definition for a custom task type, you can't specify activation conditions\. When using the Amazon A2I API to create a flow definition for a custom task type, you can't set the `HumanLoopActivationConditions` attribute of the `HumanLoopActivationConditionsConfig` parameter\. To control when human reviews are initiated, specify conditions under which `StartHumanLoop` is called in your custom application\. In this case, every `StartHumanLoop` invocation results in a human review\. For more information, see [Use Amazon Augmented AI with Custom Task Types](a2i-task-types-custom.md)\.


## Create and Start a Human Loop

- **Important**  
Amazon A2I requires all S3 buckets that contain human loop input image data to have a CORS policy attached\. To learn more about this change, see [CORS Permission Requirement](a2i-permissions-security.md#a2i-cors-update)\.
- **Important**  
When you create a human loop using a built\-in task type, you can use `DataAttributes` to specify a set of `ContentClassifiers` related to the input provided to the `StartHumanLoop` operation\. Use content classifiers to declare that your content is free of personally identifiable information or adult content\.  
To use Amazon Mechanical Turk, ensure your data is free of personally identifiable information, including protected health information under HIPAA\. Include the `FreeOfPersonallyIdentifiableInformation` content classifier\. If you do not use this content classifier, SageMaker does not send your task to Mechanical Turk\. If your data is free of adult content, also include the `'FreeOfAdultContent'` classifier\. If you do not use these content classifiers, SageMaker may restrict the Mechanical Turk workers that can view your task\.


## Permissions and Security

- **Important**  
If you do not add a CORS configuration to the S3 buckets that contains your input data, human review tasks for those input data objects fail\.
- **Note**  
You can also attach the `AmazonAugmentedAIFullAccess` policy to an IAM role that is used to create and start a human loop\.
- **Note**  
You can also attach the `AmazonAugmentedAIIntegratedAPIAccess` policy to an IAM role that is used to create and start a human loop\.

