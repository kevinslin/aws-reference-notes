---
id: Managing your service
title: Managing your service
created: 1683841041000
updated: 1683841041000
---
# Managing your service

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-app-runner-developer-guide.git)
{% endhint %}

## Creation

- **Note**  
An access role isn't required if your image is stored in Amazon ECR Public, where images are publicly available\.
- **Important**  
The failed service isn't usable\. You don't incur any additional charges for it beyond the initial creation attempt\. However, App Runner doesn't automatically delete the failed service, and it still counts towards your service quota\. When you're done analyzing the failure, make sure that you delete the failed service\.


## Custom domain names

- **Note**  
You can optionally include the `www` subdomain of your domain\. However, this is currently only supported in the API\. The App Runner console doesn't support it\.


## Pausing / resuming

- **Important**  
When you pause your service, your application loses its state\. For example, any ephemeral storage that your code used is lost\. For your code, pausing and resuming your service is the equivalent of deploying to a new service\.
If you pause a service due to a flaw in your code \(for example, a discovered bug or security issue\), you can't deploy a new version before resuming the service\.  
Therefore, we recommend that you keep the service running and roll back to your last stable application version instead\.
When you resume your service, App Runner deploys the last application version that was used before you paused the service\. If you added any new source versions since pausing your service, App Runner doesn't automatically deploy them even if automatic deployment is selected\. For example, assume you have new image versions in the image repository or new commits in the code repository\. These versions aren't automatically deployed \.  
To deploy a newer version, perform a manual deployment or add another version to your source repository after resuming your App Runner service\.

