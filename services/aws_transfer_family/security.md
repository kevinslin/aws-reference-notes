---
id: Security
title: Security
created: 1683841041000
updated: 1683841041000
---
# Security

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-transfer-user-guide.git)
{% endhint %}

## Working with security policies

- **Note**  
 We support TLS 1\.2\.
- **Note**  
`TransferSecurityPolicy-2020-06` is the default security policy attached to your server when creating a server using the console\.
`TransferSecurityPolicy-2018-11` is the default security policy attached to your server when creating a server using the API or CLI\.
- **Note**  
The FIPS service endpoint and TransferSecurityPolicy\-FIPS\-2020\-06 security policy is only available in some AWS Regions\. For more information, see [AWS Transfer Family endpoints and quotas](https://docs.aws.amazon.com/general/latest/gr/transfer-service.html) in the *AWS General Reference*\.


## Cross-service confused deputy prevention

- **Note**  
In the following examples, replace each *user input placeholder* with your own information\.
- **Note**  
In our examples, we use both `ArnLike` and `ArnEquals`\. They are functionally identical, and therefore you may use either when you construct your policies\. Transfer Family documentation uses `ArnLike` when the condition contains a wildcard character, and `ArnEquals` to indicate an exact match condition\.
- **Note**  
The following examples can be used in both logging and invocation roles\.

