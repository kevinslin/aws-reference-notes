---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}
## Deployment

- **Note**  
When you upload a file directly with the AWS CLI, AWS SDK, or otherwise, the binary ZIP file is converted to base64, which increases its size by about 30%\. To allow for this, and the size of other parameters in the request, the actual request size limit that Lambda applies is larger\. Due to this, the 50 MB limit is approximate\.


## Invocation

- **Note**  
Unlike other Lambda API operations, the name of the IAM action \(`lambda:InvokeFunction`\) doesn't match the name of the API operation \(`Invoke`\) for invoking a function\.
- **Note**  
There is a known issue in which the first invocation on an initialized execution environment reports a non\-zero **Init Duration** metric in CloudWatch Logs, even though no cold start has occurred\. We're developing a fix to correct the reporting to CloudWatch Logs\.


## Execution

- **Note**  
It may take 5 to 10 minutes for logs to show up after a function invocation\.

