---
id: Managing users
title: Managing users
created: 1683841041000
updated: 1683841041000
---
# Managing users

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-transfer-user-guide.git)
{% endhint %}

## Service-managed users

- **Note**  
 If you want to configure a cross account Amazon S3 bucket, follow the steps mentioned in this Knowledge Center article: [ How do I configure my AWS Transfer Family server to use an Amazon Simple Storage Service bucket that's in another AWS account?](https://aws.amazon.com/premiumsupport/knowledge-center/sftp-cross-account-s3-bucket/)\.


## Directory services users

- **Note**  
AWS Transfer Family does not support Simple AD\.
Transfer Family does not support cross\-region Active Directory configurations: we only support Active Directory integrations that are in the same region as that of the Transfer Family server\.
Transfer Family does not support using AD Connector to enable multi\-factor authentication \(MFA\) for your existing RADIUS\-based MFA infrastructure\.
- **Note**  
If you are using AWS Directory Service as your identity provider, and if `userPrincipalName` and `SamAccountName` have different values, AWS Transfer Family accepts the value in `SamAccountName`\. Transfer Family does not accept the value specified in `userPrincipalName`\.
- **Important**  
 You can't delete a Microsoft AD directory in AWS Directory Service if you used it in a Transfer Family server\. You must delete the server first, and then you can delete the directory\.
- **Note**  
Users must belong *directly* to the group to which you are granting access\. For example, assume that Bob is a user and he belongs to groupA, and groupA itself is included in groupB\.  
If you grant access to groupA, Bob is granted access\.
 If you grant access to groupB \(and not to groupA\), Bob does not have access\.
- **Note**  
A user must be in exactly one group \(an external ID\) that is listed in the **Access** section of the **Endpoint configuration** page\. If the user is in no groups, or is in more than a single group, that user is not granted access\.
- **Note**  
You can specify the simple username\. However, in this case, the Active Directory code has to search all the directories in the federation\. This might limit the search, and authentication might fail even if the user should have access\.
- **Note**  
When you enable Azure ADDS, make sure it is configured for the resource group and the Azure AD domain to which you are connecting your SFTP Transfer server\.
- **Note**  
You can't delete a Microsoft AD directory in AWS Directory Service if you used it in a Transfer Family server\. You must delete the server first, and then you can delete the directory\.
- **Note**  
Users must belong *directly* to the group to which you are granting access\. For example, assume that Bob is a user and he belongs to groupA, and groupA itself is included in groupB\.  
If you grant access to groupA, Bob is granted access\.
 If you grant access to groupB \(and not to groupA\), Bob does not have access\.


## Custom identity provider users

- **Note**  
Before you create a Transfer Family server that uses Lambda as the identity provider, you must create the function\. For an example Lambda function, see [Default Lambda function](#authentication-lambda-examples-default)\. Or, you can deploy a CloudFormation stack that uses a [Lambda function templates](#lambda-idp-templates)\. Also, make sure your Lambda function uses a resource\-based policy that trusts Transfer Family\. For an example policy, see [Lambda resource\-based policy](#lambda-resource-policy)\.
- **Note**  
The `"Url":` line is returned only if you are using an API Gateway method as your custom identity provider\.
- **Note**  
To improve security, you can configure a web application firewall\. AWS WAF is a web application firewall that lets you monitor the HTTP and HTTPS requests that are forwarded to an Amazon API Gateway\. For details, see [Add a web application firewall](web-application-firewall.md)\.
- **Note**  
The username must be a minimum of 3 and a maximum of 100 characters\. You can use the following characters in the username: a–z, A\-Z, 0–9, underscore \(\_\), hyphen \(\-\), period \(\.\), and at sign \(@\)\. However, the username can't start with a hyphen \(\-\), period \(\.\), or at sign \(@\)\.
- **Note**  
 The policy is escaped JSON as a string\. For example:
- **Note**  
If you have multiple protocols enabled for your server and want to provide access using the same username over multiple protocols, you can do so as long as the credentials specific to the protocol have been set up in your identity provider\.  
For File Transfer Protocol \(FTP\), we recommend maintaining separate credentials from Secure Shell \(SSH\) File Transfer Protocol \(SFTP\) and File Transfer Protocol over SSL \(FTPS\)\. We recommend maintaining separate credentials for FTP because, unlike SFTP and FTPS, FTP transmits credentials in clear text\. By isolating FTP credentials from SFTP or FTPS, if FTP credentials are shared or exposed, your workloads using SFTP or FTPS remain secure\.


## Custom identity provider tutorial

- **Note**  
To improve security, you can configure a web application firewall\. AWS WAF is a web application firewall that lets you monitor the HTTP and HTTPS requests that are forwarded to an Amazon API Gateway\. For details, see [Add a web application firewall](web-application-firewall.md)\.
- **Note**  
 If you choose Amazon EFS for the storage option, you need to add a Posix Profile setting to the Lambda function\. For details, see [Update Lambda if using Amazon EFS](#lambda-posix)\.
- **Note**  
For these `sftp` commands, use the ID for the AWS Region where your Transfer Family server is located\. For example, if your server is in US East \(Ohio\), use `us-east-2`\.

