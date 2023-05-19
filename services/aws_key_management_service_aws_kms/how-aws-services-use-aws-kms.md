---
id: How AWS services use AWS KMS
title: How AWS services use AWS KMS
created: 1683841041000
updated: 1683841041000
---
# How AWS services use AWS KMS

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-kms-developer-guide.git)
{% endhint %}

## AWS CloudTrail

- **Important**  
AWS CloudTrail and Amazon S3 support only [symmetric AWS KMS keys](concepts.md#symmetric-cmks)\. You cannot use an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) to encrypt your CloudTrail Logs\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.
- **Note**  
You might need to scroll to the right to see some of the callouts in the following example log entry\.
- **Note**  
You might need to scroll to the right to see some of the callouts in the following example log entry\.
- **Note**  
You might need to scroll to the right to see some of the callouts in the following example log entry\.


## Amazon Elastic Block Store (Amazon EBS)

- **Important**  
Amazon EBS supports only [symmetric KMS keys](concepts.md#symmetric-cmks)\. You cannot use an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) to encrypt an Amazon EBS volume\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.


## Amazon Elastic Transcoder

- **Important**  
For both client\-side and server\-side encryption, Elastic Transcoder supports only [symmetric KMS keys](concepts.md#symmetric-cmks)\. You cannot use an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) to encrypt your Elastic Transcoder files\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.
- **Important**  
AWS never stores your private encryption keys\. Therefore, it is important that you manage your keys safely and securely\. If you lose them, you won't be able to decrypt your data\.


## Amazon EMR

- **Important**  
Amazon EMR supports only [symmetric KMS keys](concepts.md#symmetric-cmks)\. You cannot use an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) to encrypt data at rest in an Amazon EMR cluster\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.


## Amazon Redshift

- **Important**  
Amazon Redshift supports only symmetric encryption KMS keys\. You cannot use an asymmetric KMS key in an Amazon Redshift encryption workflow\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.


## Amazon Relational Database Service (Amazon RDS)

- **Important**  
Amazon RDS supports only [symmetric KMS keys](concepts.md#symmetric-cmks)\. You cannot use an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) to encrypt data in an Amazon RDS database\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.


## Amazon Simple Email Service (Amazon SES)

- **Important**  
Amazon SES supports only [symmetric KMS keys](concepts.md#symmetric-cmks)\. You cannot use an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) to encrypt your Amazon SES email messages\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.


## AWS Systems Manager Parameter Store

- **Important**  
Parameter Store supports only [symmetric KMS keys](concepts.md#symmetric-cmks)\. You cannot use an [asymmetric KMS key](symmetric-asymmetric.md#asymmetric-cmks) to encrypt your parameters\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.


## Amazon WorkMail

- **Important**  
Amazon WorkMail supports only symmetric encryption KMS keys\. You cannot use an asymmetric KMS key to encrypt data in Amazon WorkMail\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.
- **Note**  
Amazon WorkMail uses a symmetric mailbox encryption key to protect message keys\. Previously, Amazon WorkMail protected each mailbox with an asymmetric key pair\. It used the public key to encrypt each message key and the private key to decrypt it\. The private mailbox key was protected by the KMS key for the organization\. Existing mailboxes might still use an asymmetric mailbox key pair\. This change does not affect the security of the mailbox or its messages\.


## WorkSpaces

- **Important**  
WorkSpaces supports only symmetric encryption KMS keys\. You cannot use an asymmetric KMS key to encrypt the volumes in an WorkSpaces\. For help determining whether a KMS key is symmetric or asymmetric, see [Identifying asymmetric KMS keys](find-symm-asymm.md)\.

