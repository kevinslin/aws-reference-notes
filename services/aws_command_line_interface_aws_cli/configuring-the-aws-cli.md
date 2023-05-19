---
id: Configuring the AWS CLI
title: Configuring the AWS CLI
created: 1683841041000
updated: 1683841041000
---
# Configuring the AWS CLI

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cli-user-guide.git)
{% endhint %}

## Configuration and credential file settings

- **Note**  
These settings are entirely optional\. You should be able to successfully use the `aws s3` transfer commands without configuring any of these settings\. These settings are provided to enable you to tune for performance or to account for the specific environment where you are running these `aws s3` commands\.


## Command completion

- **Note**  
Command completion is automatically configured and enabled by default on Amazon EC2 instances that run Amazon Linux\.
- **Note**  
For information on how PowerShell handles their completion, including their various completion keys, see [about\_Tab\_Expansion](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_tab_expansion?view=powershell-7.1) in the *Microsoft PowerShell Docs*\.


## Using an HTTP proxy

- **Note**  
The following examples show the environment variable name in all uppercase letters\. However, if you specify a variable twice using different cases, the lowercase letters take precedence\. We recommend that you define each variable only once to avoid system confusion and unexpected behavior\.
- **Note**  
The AWS CLI doesn't support NTLM proxies\. If you use an NTLM or Kerberos protocol proxy, you might be able to connect through an authentication proxy like [Cntlm](http://cntlm.sourceforge.net)\.

