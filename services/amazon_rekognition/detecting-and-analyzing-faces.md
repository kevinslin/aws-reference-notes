---
id: Detecting and analyzing faces
title: Detecting and analyzing faces
created: 1683841041000
updated: 1683841041000
---
# Detecting and analyzing faces

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rekognition-developer-guide.git)
{% endhint %}

## Comparing faces in images

- **Note**  
CompareFaces uses machine learning algorithms, which are probabilistic\. A false negative is an incorrect prediction that a face in the target image has a low similarity confidence score when compared to the face in the source image\. To reduce the probability of false negatives, we recommend that you compare the target image against multiple source images\. If you plan to use `CompareFaces` to make a decision that impacts an individual's rights, privacy, or access to services, we recommend that you pass the result to a human for review and further validation before taking action\.


## Detecting faces in a stored video

- **Note**  
If you've already run a video example other than [Analyzing a video stored in an Amazon S3 bucket with Java or Python \(SDK\)](video-analyzing-with-sqs.md), the function name to replace is different\.

