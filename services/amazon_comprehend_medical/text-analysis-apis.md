---
id: Text analysis APIs
title: Text analysis APIs
created: 1683841041000
updated: 1683841041000
---
# Text analysis APIs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-comprehend-medical-developer-guide.git)
{% endhint %}

## Detect entities (Version 2)

- **Important**  
Amazon Comprehend Medical provides confidence scores that indicate the level of confidence in the accuracy of detected entities\. When you are identifying protected health information \(PHI\), evaluate these scores and identify the right confidence threshold for your use case\. Use high\-confidence thresholds in situations that require high accuracy\. For certain use cases, results should be reviewed and verified by appropriately trained human reviewers\. Use Amazon Comprehend Medical in patient care scenarios only after review by trained medical professionals for accuracy and exercising medical judgment\.


## Detect entities

- **Note**  
This version of the **DetectEntities** operation should not be used for new applications\. You should use version 2 of the operation instead\. All new iterations and enhancements of features will be specific to Detect Entities Version 2\. For more information, see [Detect entities \(Version 2\)](textanalysis-entitiesv2.md)\.
- **Important**  
Amazon Comprehend Medical provides confidence scores that indicate the level of confidence in the accuracy of detected entities\. When you are identifying protected health information \(PHI\), evaluate these scores and identify the right confidence threshold for your use case\. Use high confidence thresholds in situations that require high accuracy\. For certain use cases, results should be reviewed and verified by appropriately trained human reviewers\. Results from Amazon Comprehend Medical in patient care scenarios should only be used after review by trained medical professionals reviewing results for accuracy and sound medical judgment\.


## Detect PHI

- **Important**  
 Amazon Comprehend Medical provides confidence scores that indicate the level of confidence in the accuracy of the detected entities\. Evaluate these confidence scores and identify the right confidence threshold for your use case\. For specific compliance use cases, we recommend that you use additional human review or other methods to confirm the accuracy of detected PHI\.

