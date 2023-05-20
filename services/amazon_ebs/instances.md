---
id: Instances
title: Instances
created: 1683841041000
updated: 1683841041000
---
# Instances

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-ec2-user-guide.git)
{% endhint %}

## Instances and AMIs

- **Note**  
Some AWS resources, such as Amazon EBS volumes and Elastic IP addresses, incur charges regardless of the instance's state\. For more information, see [Avoiding Unexpected Charges](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/checklistforunwantedcharges.html) in the *AWS Billing User Guide*\. For more information about Amazon EBS costs, see [Amazon EBS pricing](http://aws.amazon.com/ebs/pricing/)\.


## Instance types

- **Note**  
Previous generation instances are still fully supported and retain the same features and functionality\. We encourage you to use the latest generation of instances to get the best performance\.


## Mac instances

- **Note**  
The **unit of billing** is the **dedicated host**\. The instances running on that host have no additional charge\.
- **Important**  
Multiple users can access the OS simultaneously\. Typically there is a 1:1 user:GUI session due to the built\-in Screen Sharing service on port 5900\. Using SSH within macOS supports multiple sessions up until the "Max Sessions" limit in the sshd\_config file\.
- **Note**  
macOS 10\.14 and later only allows control if Screen Sharing is enabled through [System Preferences](https://support.apple.com/guide/remote-desktop/enable-remote-management-apd8b1c65bd/mac)\.
- **Note**  
The current build of displayplacer is not supported on M1 Mac instances\.
- **Note**  
With this procedure on macOS Big Sur, you can only perform minor updates such as updating from macOS Big Sur 11\.7\.3 to macOS Big Sur 11\.7\.4\. For macOS Monterey or above, you can perform major software updates\.
- **Note**  
Do not exit this SSH session until the following VNC connection and GUI steps are completed\. When the instance is restarted, the connection will close automatically\.
- **Note**  
EC2 System Monitoring for macOS is not currently supported on M1 Mac instances\.


## Instance lifecycle

- **Note**  
The table indicates billing for instance usage only\. Some AWS resources, such as Amazon EBS volumes and Elastic IP addresses, incur charges regardless of the instance's state\. For more information, see [Avoiding Unexpected Charges](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/checklistforunwantedcharges.html) in the *AWS Billing User Guide*\.
- **Note**  
Rebooting an instance doesn't start a new instance billing period because the instance stays in the `running` state\.


## Amazon EI

- **Note**  
Starting April 15, 2023, AWS will not onboard new customers to Amazon Elastic Inference \(EI\), and will help current customers migrate their workloads to options that offer better price and performance\. After April 15, 2023, new customers will not be able to launch instances with Amazon EI accelerators in Amazon SageMaker, Amazon ECS, or Amazon EC2\. However, customers who have used Amazon EI at least once during the past 30\-day period are considered current customers and will be able to continue using the service\.

