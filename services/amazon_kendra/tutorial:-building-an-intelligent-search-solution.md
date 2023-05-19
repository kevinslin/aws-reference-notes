---
id: 'Tutorial: Building an intelligent search solution'
title: 'Tutorial: Building an intelligent search solution'
created: 1683841041000
updated: 1683841041000
---
# Tutorial: Building an intelligent search solution

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-kendra-developer-guide.git)
{% endhint %}

## Step 1: Adding documents

- **Important**  
The name of an Amazon S3 bucket must be unique across all of AWS\.
- **Note**  
You must choose a region that supports both Amazon Comprehend and Amazon Kendra\. You cannot change the region of a bucket after you have created it\.


## Step 3: Formatting the metadata

- **Important**  
For the metadata to be formatted correctly, the input values in steps 8\-10 must be exact\.
- **Note**  
If you do not have Boto3 installed, run `pip3 install boto3` to install it\.
- **Important**  
For the metadata to be formatted correctly, the input values in steps 5\-7 must be exact\.


## Step 4: Creating an index and ingesting the metadata

- **Important**  
Misspelled entity types will not be recognized by the index\.

