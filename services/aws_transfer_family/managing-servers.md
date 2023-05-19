---
id: Managing servers
title: Managing servers
created: 1683841041000
updated: 1683841041000
---
# Managing servers

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-transfer-user-guide.git)
{% endhint %}

## Edit server details

- **Note**  
If Transfer Family created a CloudWatch logging IAM role for you when you created a server, the IAM role is called `AWSTransferLoggingAccess`\. You can use it for all your servers\.
- **Important**  
If you aren't planning to migrate existing users from an existing SFTP\-enabled server to a new SFTP\-enabled server, ignore this section\. Accidentally changing a server's host key can be disruptive\.
- **Note**  
Although the Transfer Family console allows you to specify and add server host keys for all servers, these keys are only useful for servers that use the SFTP protocol\.
- **Note**  
Transfer Family uses the first added key for each algorithm as the active host key\. You can associate up to 10 host keys per SFTP server, but only one key per algorithm is active at any specific time\.
- **Note**  
When you stop a server to take it offline, currently you are still accruing service charges for that server\. To eliminate additional server\-based charges, delete that server\.

