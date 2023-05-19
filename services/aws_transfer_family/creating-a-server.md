---
id: Creating a server
title: Creating a server
created: 1683841041000
updated: 1683841041000
---
# Creating a server

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-transfer-user-guide.git)
{% endhint %}

## Create an SFTP-enabled server

- **Note**  
SFTP servers for Transfer Family operate over port 22\.


## Create a server in a VPC

- **Note**  
 After May 19, 2021, you won't be able to create a server using `EndpointType=VPC_ENDPOINT` in your AWS account if your account hasn't already done so before May 19, 2021\. If you have already created servers with `EndpointType=VPC_ENDPOINT` in your AWS account on or before February 21, 2021, you will not be affected\. After this date, use `EndpointType`=**VPC**\. For more information, see [Discontinuing the use of VPC\_ENDPOINT](#deprecate-vpc-endpoint)\.
- **Note**  
Only SFTP and FTPS can be used on an internet\-facing VPC hosted endpoint\.
- **Note**  
When your server in a VPC is online, only the subnets can be modified and only through the [UpdateServer](https://docs.aws.amazon.com/transfer/latest/userguide/API_UpdateServer.html) API\. You must [stop the server](edit-server-config.md#edit-online-offline) to add or change the server endpoint's Elastic IP addresses\.
- **Note**  
If you have an existing server in a VPC displayed as `VPC_ENDPOINT`, we recommend that you modify it to the new VPC endpoint type\. With this new endpoint type, you no longer need to use a Network Load Balancer \(NLB\) to associate Elastic IP addresses with your server's endpoint\. Also, you can use VPC security groups to restrict access to your server's endpoint\. However, you can continue to use the `VPC_ENDPOINT` endpoint type as needed\.
- **Note**  
We do not plan to add these features and FTPS or FTP support to EndpointType=VPC\_ENDPOINT\. We are no longer offering it as an option on the AWS Transfer Family Console\.


## Working with custom hostnames

- **Note**  
If your server has a VPC endpoint, then the format for the hostname is different from the one described above\. To find your VPC endpoint, select the VPC on the server's details page, then select the **VPC endpoint ID** on the VPC dashboard\. The endpoint is the first DNS name of those listed\.
- **Note**  
You also need to create a DNS record to redirect traffic from your domain to your server endpoint\.
- **Note**  
 Your public, hosted zones and their IDs are available on Amazon Route 53\.   
Sign in to the AWS Management Console and open the Route 53 console at [https://console\.aws\.amazon\.com/route53/](https://console.aws.amazon.com/route53/)\.

