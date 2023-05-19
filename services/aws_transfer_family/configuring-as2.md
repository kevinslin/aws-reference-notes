---
id: Configuring AS2
title: Configuring AS2
created: 1683841041000
updated: 1683841041000
---
# Configuring AS2

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-transfer-user-guide.git)
{% endhint %}

## AS2 example setup

- **Note**  
Your version of this command contains the actual values for the `TransferS3BucketName` and `TransferConnectorId` resources in your stack\.
- **Note**  
Some portions of the example setup use the AWS Command Line Interface \(AWS CLI\)\. If you haven't already installed the AWS CLI, see [Installing or updating the latest version of the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) in the *AWS Command Line Interface User Guide*\.
- **Note**  
Some AS2\-enabled servers, such as OpenAS2, require that you use the same certificate for both signing and encryption\. In this case, you can import the same private key and certificate for both purposes\. To do so, run this command instead of the two previous commands:
- **Note**  
 Many of the example steps use commands that load parameters from a file\. For more details about using files to load parameters, see [ How to load parameters from a file](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-parameters-file.html)\.
- **Note**  
Even though the logging role is optional, we highly recommend setting it up so that you can see the status of your messages and troubleshoot configuration issues\.
- **Note**  
In the previous commands, replace *MYCORP* with the name of your organization, and *PARTNER\-COMPANY* with the name of your trading partner's organization\.
- **Note**  
To find details for your connectors, run the command `aws transfer list-connectors`\. This command returns the connector ID, URL, and ARN for your connectors\. Then, you can run the command `aws transfer describe-connector --connector-id your-connector-id`, with the ID that you want to use\. This command returns all of the details for `your-connector-id`\.


## AS2 configurations

- **Important**  
Manage access to your server from client IP addresses using the [network access control lists \(network ACLs\)](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html) for the subnets configured on the load balancer\. Network ACL permissions are set at the subnet level, so the rules apply to all resources using the subnet\. You can't control access from client IP addresses using security groups because the load balancer's target type is set to IP instead of Instance\. This means that the load balancer doesn't preserve source IP addresses\. If the [Network Load Balancer's health checks](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/target-group-health-checks.html) fail, this means the load balancer can't connect to the server endpoint\. To troubleshoot this, check the following:  
Confirm that the server [endpoint's associated security group](https://aws.amazon.com/premiumsupport/knowledge-center/sftp-enable-elastic-ip-custom-port/) allows inbound connections from the subnets configured on the load balancer\. The load balancer must be able to connect to the server endpoint over port 5080\.
Confirm that the server's **State** is **Online**\.

