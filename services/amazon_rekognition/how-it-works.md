---
id: How it works
title: How it works
created: 1683841041000
updated: 1683841041000
---
# How it works

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rekognition-developer-guide.git)
{% endhint %}

## Types of analysis

- **Note**  
For information about Amazon Rekognition Custom Labels, see the [Amazon Rekognition Custom Labels Developer Guide](https://docs.aws.amazon.com/rekognition/latest/customlabels-dg/what-is.html)\.


## Non-storage and storage API operations

- **Note**  
The service does not persist actual image bytes\. Instead, the underlying detection algorithm first detects the faces in the input image, extracts facial features into a feature vector for each face, and then stores it in the database\. Amazon Rekognition uses these feature vectors when performing face matches\.

