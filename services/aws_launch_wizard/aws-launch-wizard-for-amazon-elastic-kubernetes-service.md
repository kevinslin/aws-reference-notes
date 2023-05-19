---
id: AWS Launch Wizard for Amazon Elastic Kubernetes Service
title: AWS Launch Wizard for Amazon Elastic Kubernetes Service
created: 1683841041000
updated: 1683841041000
---
# AWS Launch Wizard for Amazon Elastic Kubernetes Service

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-launch-wizard-user-guide.git)
{% endhint %}

## Test the deployment

- **Important**  
You must run these steps from a network that has access to the Kubernetes API, as configured by the **Amazon EKS public access endpoint** and **Kubernetes API public access CIDR** parameters\. For more information, see [Installing kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html) in the **Amazon EKS User Guide**\. If you enabled the optional bastion host, you can connect to it by using SSH\. Use the key pair that you specified during deployment and the IP address from the **Outputs** tab of the AWS CloudFormation stack\. The bastion host already has `kubectl` installed and configured so that it connects to the cluster\. To test the CLI, connect to the cluster, and run the command, shown in step 1\.


## Troubleshoot

- **Note**  
When you enable **Deactivate rollback on failed deployment**, you continue to incur AWS charges for the stack\. Ensure that you delete the stack when you finish troubleshooting\.

