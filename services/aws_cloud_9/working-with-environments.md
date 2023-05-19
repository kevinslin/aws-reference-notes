---
id: Working with environments
title: Working with environments
created: 1683841041000
updated: 1683841041000
---
# Working with environments

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## Accessing no-ingress EC2 instances with Systems Manager

- **Important**  
There are no additional charges for using Systems Manager Session Manager to manage connections to your EC2 instance\.
- **Important**  
The option to use Systems Manager for no\-ingress connections is currently available only when creating new EC2 environments\.
- **Important**  
Currently, if the EC2 instance for your environment is launched into a private subnet, you can't use [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials) to allow the EC2 environment to access an AWS service on behalf of an AWS entity \(an IAM user, for example\)\.
- **Important**  
 If you create a no\-ingress EC2 environment for the first time with AWS CLI, you must explicitly define the required service role and instance profile\. For more information, see [Managing instance profiles for Systems Manager with the AWS CLI](#aws-cli-instance-profiles)\.
- **Note**  
 If you no longer need to use Systems Manager to access an instance, you can delete the `AWSCloud9SSMAccessRole` service role\. For more information, see [Deleting roles or instance profiles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_manage_delete.html) in the *IAM User Guide*\.
- **Note**  
The following managed policies also include these policy statements: `AWSCloud9Administrator`, `AWSCloud9User`, and `AWSCloud9EnvironmentMember`\.
- **Note**  
If you try to create an AWS CloudFormation stack for a no\-ingress EC2 environment without first creating the required service role and instance profile, the stack isn't created and the following error message is displayed:   
Instance profile AWSCloud9SSMInstanceProfile does not exist in account\.
- **Note**  
 If you don't add permissions to start a Session Manager session before creating a stack for a no\-ingress EC2 environment, an `AccessDeniedException` error is returned\.
- **Note**  
You can create and configure VPC endpoints using the AWS Management Console, AWS CLI, or Amazon VPC API\. The procedure below explains how to create a VPC endpoint using the console interface\.<a name="create-s3-endpoint"></a>


## Opening an environment

- **Note**  
This procedure assumes you have already created an AWS Cloud9 development environment\. To create an environment, see [Creating an Environment](create-environment.md)\.


## Call AWS services from an Environment

- **Note**  
You can't use this procedure for an AWS Cloud9 SSH development environment\. Instead, skip ahead to [Create and Store Permanent Access Credentials in an Environment](#credentials-permanent-create)\.  
We recommend that you use AWS managed temporary credentials instead of an instance profile\. Follow these instructions only if for some reason you can't use AWS managed temporary credentials\. For more information, see [AWS Managed Temporary Credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials)\.
- **Note**  
If you already have an IAM role that contains an instance profile, skip ahead to [Attach an Instance Profile to an Instance with the Amazon EC2 Console](#credentials-temporary-attach-console)\.
- **Note**  
If you already have an IAM role that contains an instance profile, skip ahead to [Attach an Instance Profile to an Instance with the AWS CLI](#credentials-temporary-attach-cli)\.  
For this topic, we recommend you configure the AWS CLI using IAM administrator\-level credentials in your AWS account\. If you cannot do this, check with your AWS account administrator\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
The **AdministratorAccess** policy allows unrestricted access to all AWS actions and resources across your AWS account\. It should be used only for experimentation purposes\. For more information, see [IAM Policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) in the *IAM User Guide*\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
If you're using an AWS Cloud9 EC2 development environment, we recommend that you use AWS managed temporary credentials instead of AWS permanent access credentials\. To work with AWS managed temporary credentials, see [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials)\.
- **Note**  
For this section, we recommend that you configure the AWS CLI using IAM administrator\-level credentials in your AWS account\. If you cannot do this, check with your AWS account administrator\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
The following procedure shows how to store your permanent access credentials by using environment variables\. If you have the AWS CLI or the aws\-shell installed in your environment, you can use the ** `aws configure` ** command for the AWS CLI or the ** `configure` ** command for the aws\-shell to store your permanent access credentials instead\. For instructions, see [Quick Configuration](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html#cli-quick-configuration) in the *AWS Command Line Interface User Guide*\.


## Changing Environment Settings

- **Note**  
For more information, see [Project Setting Changes You Can Make](settings-project.md#settings-project-change)\.


## Working with Shared Environments

- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
If you're using [AWS managed temporary credentials](security-iam.md#auth-and-access-control-temporary-managed-credentials), you can't use a terminal session in the AWS Cloud9 IDE to run some or all of the commands in this section\. To address AWS security best practices, AWS managed temporary credentials don’t allow some commands to be run\. Instead, you can run those commands from a separate installation of the AWS Command Line Interface \(AWS CLI\)\.
- **Note**  
If you're using the aws\-shell, omit the `aws` prefix from the preceding commands\.
- **Note**  
If the **Collaborate** window isn't visible, choose the **Collaborate** button\. If the **Collaborate** button isn't visible, on the menu bar, choose **Window, Collaborate**\.
- **Note**  
When you delete a chat message, it is deleted from the environment for all members\.
- **Note**  
When you delete all chat messages, they are deleted from the environment for all members\.
- **Note**  
You cannot remove your user from an environment if you're the environment owner\.  
Removing your user from an environment doesn't remove your user from IAM\.
- **Note**  
To remove any member other than your user from an environment, you must be signed in to AWS Cloud9 using the credentials of the environment owner\.  
Removing a member does not remove the user from IAM\.


## Moving an environment and resizing/encrypting Amazon EBS volumes

- **Note**  
This topic only describes moving an environment from one Amazon EC2 instance to another or resizing an Amazon EBS volume\. To resize an environment from one of your own servers to another or to change the storage space for one of your own servers, refer to your server's documentation\.
- **Important**  
If your AWS Cloud9 IDE uses Amazon EBS volumes that are encrypted by default, the AWS Identity and Access Management service\-linked role for AWS Cloud9 requires access to the AWS KMS key for these EBS volumes\. If access is not provided, the AWS Cloud9 IDE might fail to launch and debugging might be difficult\.  
To provide access, add the service\-linked role for AWS Cloud9, `AWSServiceRoleForAWSCloud9`, to the KMS key that's used by your Amazon EBS volumes\. For more information on this task, see [Create an AWS Cloud9 IDE that uses Amazon EBS volumes with default encryption](https://docs.aws.amazon.com/prescriptive-guidance/latest/patterns/create-an-aws-cloud9-ide-that-uses-amazon-ebs-volumes-with-default-encryption.html) in *AWS Prescriptive Guidance Patterns*\.
- **Note**  
The following procedure focuses on using a customer managed key to encrypt a volume\. You can also use an AWS managed key for an AWS service in your account \(the alias for Amazon EBS is `aws/ebs`\)\. If you choose this default option for encryption, skip step 1 where you create a customer managed key\. Also skip step 8 where you update the key policy \(you can't change the key policy for an AWS managed key\)\.<a name="creating-encrypted-volume"></a>

