---
id: Amazon A2I and Amazon Textract
title: Amazon A2I and Amazon Textract
created: 1683841041000
updated: 1683841041000
---
# Amazon A2I and Amazon Textract

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-textract-developer-guide.git)
{% endhint %}

## Core Concepts of Amazon A2I

- **Note**  
You can further customize the conditions under which documents are sent to humans for review using the Amazon A2I custom task type\. With this task type, you specify conditions for a human review directly in your application\. For information , see [Use Amazon Augmented AI with Custom Task Types](https://docs.aws.amazon.com/sagemaker/latest/dg/a2i-task-types-custom.html) in the Amazon SageMaker Developer Guide\.
- **Important**  
Click [here](https://aws.amazon.com/compliance/services-in-scope/) to see the compliance programs that cover Amazon Augmented AI at this time\. If you use Amazon Augmented AI in conjunction with other AWS services \(such as Amazon Rekognition and Amazon Textract\), please note that Amazon Augmented AI may not be in scope for the same compliance programs as those other services\. You are responsible for how you use Amazon Augmented AI, including understanding how the service will process or store customer data, and any impact on the compliance of your data environment\. You should discuss your workload objectives and goals with your AWS account team; they can help you evaluate whether the service is a good fit for your proposed use case and architecture\.  
Currently, Amazon Augmented AI is PCI compliant except for public and vendor workforce cases\.  
For information regarding Amazon Augmented AI HIPAA compliance, click [here](https://aws.amazon.com/blogs/machine-learning/amazon-augmented-ai-is-now-a-hipaa-eligible-service/)\.


## Get Started Using Amazon A2I

- **Note**  
This section explains how to create a human review workflow for the Amazon A2I, Amazon Textract task type\. To further customize Amazon A2I and Amazon Textract integration, you can use the Amazon A2I custom task type\. With this option, you provide a custom worker task template and specify the conditions under which a document is sent for human review directly in your application\. For information, see [Use Amazon Augmented AI with Custom Task Types](https://docs.aws.amazon.com/sagemaker/latest/dg/a2i-task-types-custom.html) in the *Amazon SageMaker Developer Guide*\.

