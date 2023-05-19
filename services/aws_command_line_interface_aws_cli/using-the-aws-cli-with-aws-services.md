---
id: Using the AWS CLI with AWS Services
title: Using the AWS CLI with AWS Services
created: 1683841041000
updated: 1683841041000
---
# Using the AWS CLI with AWS Services

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cli-user-guide.git)
{% endhint %}

## S3 Glacier

- **Note**  
For command reference and additional examples, see `[aws glacier](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/glacier/index.html)` in the *AWS CLI Command Reference*\.
- **Note**  
All S3 Glacier commands require an account ID parameter\. Use the hyphen character \(`--account-id -`\) to use the current account\.
- **Note**  
[HJ\-Split](http://www.hjsplit.org/) is a free file splitter for Windows and many other platforms\.
- **Note**  
The previous example uses the dollar sign \(`$`\) to reference the contents of the `UPLOADID` shell variable on Linux\. On the Windows command line, use a percent sign \(%\) on either side of the variable name \(for example, `%UPLOADID%`\)\.
- **Note**  
Windows users can use the `type` command in place of `cat`\. OpenSSL is available for Windows at [OpenSSL\.org](https://www.openssl.org/related/binaries.html)\.
- **Note**  
Vault status is updated about once per day\. See [Working with Vaults](https://docs.aws.amazon.com/amazonglacier/latest/dev/working-with-vaults.html) for more information\.

