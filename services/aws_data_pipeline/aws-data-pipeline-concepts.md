---
id: AWS Data Pipeline Concepts
title: AWS Data Pipeline Concepts
created: 1683841041000
updated: 1683841041000
---
# AWS Data Pipeline Concepts

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-data-pipeline-developer-guide.git)
{% endhint %}

## Pipeline Components, Instances, and Attempts

- **Note**  
Retrying failed tasks is an important part of a fault tolerance strategy, and AWS Data Pipeline definitions provide conditions and thresholds to control retries\. However, too many retries can delay detection of an unrecoverable failure because AWS Data Pipeline does not report failure until it has exhausted all the retries that you specify\. The extra retries may accrue additional charges if they are running on AWS resources\. As a result, carefully consider when it is appropriate to exceed the AWS Data Pipeline default settings that you use to control re\-tries and related settings\.


## Resources

- **Note**  
The limit is one instance per `Ec2Resource` component object\.

