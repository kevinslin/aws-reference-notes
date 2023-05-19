---
id: Advanced topics
title: Advanced topics
created: 1683841041000
updated: 1683841041000
---
# Advanced topics

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## Amazon VPC settings

- **Note**  
For the following procedures, if you use the Amazon VPC or Amazon EC2 consoles, we recommend that you sign in to the AWS Management Console and open the Amazon VPC console \([https://console\.aws\.amazon\.com/vpc](https://console.aws.amazon.com/vpc)\) or Amazon EC2 console \([https://console\.aws\.amazon\.com/ec2](https://console.aws.amazon.com/ec2)\) using credentials for an IAM administrator in your AWS account\.  
If you use the AWS CLI or the aws\-shell, we recommend you configure the AWS CLI or the aws\-shell with the credentials for an IAM administrator in your AWS account\. If you can't do this, check with your AWS account administrator\.
- **Important**  
If you're launching your environment's EC2 instance into a private subnet, make sure that outbound traffic is allowed for that instance so that it can connect to the SSM service\. For private subnets, outbound traffic is usually configured through a network address translation \(NAT\) gateway or VPC endpoints\. \(A NAT gateway requires a public subnet\)\.  
If you choose VPC endpoints instead of a NAT gateway for accessing SSM, automatic updates and security patches for your instance might not work if they depend on internet access\. You can use other applications, such as [AWS Systems Manager Patch Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-patch.html), to manage any software updates that your environment might require\. AWS Cloud9 software will be updated as normal\.
- **Important**  
If a security group for an instance doesn't have an inbound rule, this means no incoming traffic originating from another host to the instance is allowed\. For information about using no\-ingress EC2 instances, see [Accessing no\-ingress EC2 instances with AWS Systems Manager](ec2-ssm.md)\.
- **Note**  
For EC2 environments created on or after July 31 2018, AWS Cloud9 adds an inbound rule to restrict inbound IP addresses using SSH over port 22 to only those addresses that AWS Cloud9 uses\. For more information, see [Inbound SSH IP address ranges for AWS Cloud9](ip-ranges.md)\.
- **Note**  
For this procedure, we recommend that you sign in to the AWS Management Console and open the Amazon VPC console using credentials for an IAM administrator in your AWS account\. If you can't do this, check with your AWS account administrator\.  
Some organizations may not allow you to create VPCs on your own\. If you can't create a VPC, check with your AWS account administrator or network administrator\.
- **Important**  
The AWS account must already have a compatible VPC in the same AWS Region for the environment\. For more information, see the VPC requirements in [Amazon VPC requirements for AWS Cloud9](#vpc-settings-requirements)\.
For this procedure, we recommend that you sign in to the AWS Management Console, and then open the Amazon VPC console using credentials for an IAM administrator in your AWS account\. If you can't do this, check with your AWS account administrator\.
Some organizations might not allow you to create subnets on your own\. If you cannot create a subnet, check with your AWS account administrator or network administrator\.<a name="create-subnet-proc"></a>
- **Note**  
Even if the instance for your environment is launched in a private subnet, your VPC must feature at least one public subnet\. This is because the NAT gateway that forwards traffic to and from the instance must be hosted in a public subnet\.
- **Important**  
If your development environment is [using SSM to access an EC2 instance](ec2-ssm.md), ensure that the instance is assigned a public IP address by the public subnet it's launched into\. To do so, you can specify your own IP address or enable the automatic assignment of a public IP address\. For the steps involved in modifying auto\-assign IP settings, see [IP Addressing in your VPC](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-ip-addressing.html) in the *Amazon VPC User Guide*\.
- **Important**  
Currently, if your environment’s EC2 instance is launched into a private subnet, you can't use [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials) to allow the EC2 environment to access an AWS service on behalf of an AWS entity \(an IAM user, for example\)\.


## SSH environment host requirements

- **Note**  
Launching an Amazon EC2 instance might result in possible charges to your AWS account for Amazon EC2\. For more information, see [Amazon EC2 Pricing](https://aws.amazon.com/ec2/pricing/)\.


## Inbound SSH IP address ranges

- **Note**  
You can restrict incoming traffic to only the IP address ranges that AWS Cloud9 uses to connect over SSH\. For an EC2 environment created on or after July 31 2018, you can skip this topic\. This is because AWS Cloud9 automatically restricts inbound SSH traffic for that environment to only those IP addresses that are described later in this topic\. AWS Cloud9 does this by automatically adding a rule to the security group that's associated with the Amazon EC2 instance for the environment\. This rule restricts inbound SSH traffic over port 22 to only those IP addresses for the associated AWS Region\. For your own servers in your network you still have to follow the steps described later in this topic\.
- **Note**  
See [below](#non-file-IP) for IP address ranges for the Asia Pacific \(Hong Kong\), Europe \(Milan\), and Middle East \(Bahrain\) Regions thataren't currently included in the `ip-ranges.json` file\.
- **Note**  
Each Region has two IP address ranges to support the AWS Cloud9 control plane \(information routing\) and data plane \(information processing\) services\.


## AMI contents

- **Important**  
If your environment's Amazon EC2 instance is based on an Amazon Linux 2 AMI or an Amazon Linux AMI template, security updates are installed on the instance immediately after it's launched\. And security patches are then automatically applied to the instance every hour\. These updates are applied by a background process and don't affect your use of the instance\.  
For an Ubuntu EC2 environment, security updates are also installed on the instance immediately after it's launched\. Then the `unattended-upgrades` package automatically installs available updates daily\.
- **Important**  
We recommend that you choose the **Amazon Linux 2** option when [creating an Amazon EC2 environment using the console](create-environment-main.md#create-environment-console)\. As well as providing a secure, stable, and high\-performance runtime environment, Amazon Linux 2 AMI includes long\-term support through 2023\.  
The standard support for the previous version of Amazon Linux AMI was discontinued on December 31,2020\. Now this previous version only receives maintenance support\. For more information, see the [Amazon Linux 2 page](https://aws.amazon.com/amazon-linux-2/)\.  
Unless otherwise specified, references to Amazon Linux in this topic refer to both Amazon Linux and Amazon Linux 2 instances\.
- **Note**  
With Amazon Linux 2, you can use the Extras Library to install application and software updates on your instances\. These software updates are known as topics\. For more information, see [Extras library \(Amazon Linux 2\)](Amazon EC2 User Guide for Linux Instancesamazon-linux-ami-basics.html#extras-library) in the *Amazon EC2 User Guide for Linux Instances*\.


## Service-linked roles

- **Important**  
 If you're using License Manager and you receive an `unable to access your environment` error, you need to replace the old service\-linked role with the version that does support License Manager\. You can replace the old role simply by deleting it\. The updated role is then created automatically\.


## Logging API calls with CloudTrail

- **Note**  
Some CloudTrail events for AWS Cloud9 are not triggered by public API operations\. Instead, the following events are initiated by internal updates affecting user authentication and managed temporary credentials:  
`DisableManagedCredentialsByCollaborator`
`EnvironmentTokenSuccessfullyCreated`
`ManagedCredentialsUpdatedOnEnvironment`


## Tags

- **Note**  
When you update tags to the AWS CloudFormation stack, those updates are automatically propagated to the Amazon EC2 instance and Amazon EC2 security groups that are associated with the stack\.

