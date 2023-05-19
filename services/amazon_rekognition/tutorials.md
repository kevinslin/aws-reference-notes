---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rekognition-developer-guide.git)
{% endhint %}

## Using Amazon Rekognition and Lambda to tag assets in an Amazon S3 bucket

- **Note**  
The services you use in this tutorial are part of the AWS Free Tier\. When you are done with the tutorial, we recommend terminating any resources you created during the tutorial so that you are not charged\.
- **Note**  
Make sure you assign your bucket name to the **bucketName** variable\.
- **Note**  
Notice the use of the **maven\-shade\-plugin** in the project’s POM file\. This plugin is responsible for creating a JAR that contains the required dependencies\. If you attempt to package up the project without this plugin, the required dependences are not included in the JAR file and you will encounter a **ClassNotFoundException**\.


## Creating an Amazon Rekognition Lambda function

- **Note**  
This tutorial uses the AWS SDK for Java 1\.x\. For a tutorial using Rekognition and the AWS SDK for Java version 2, see the [AWS Documentation SDK examples GitHub repository](https://github.com/awsdocs/aws-doc-sdk-examples/tree/master/javav2/usecases/video_analyzer_application)\.
- **Note**  
Use the same AWS Region throughout the tutorial\.

