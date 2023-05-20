---
id: Certificate administration
title: Certificate administration
created: 1683841041000
updated: 1683841041000
---
# Certificate administration

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-private-ca-user-guide.git)
{% endhint %}

## Issuing private end-entity certificates

- **Note**  
Certificates created with the procedure below, using the issue\-certificate command, or with the [IssueCertificate](https://docs.aws.amazon.com/acm/latest/APIReference/API_RequestCertificate.html) API action, cannot be exported for use outside AWS\. However, you can use your private CA to sign certificates issued through ACM, and those certificates can be exported along with their secret keys\. For more information, see [Requesting a private certificate](https://docs.aws.amazon.com/acm/latest/userguide/gs-acm-request-private.html) and [Exporting a private certificate](https://docs.aws.amazon.com/acm/latest/userguide/export-private.html) in the *ACM User Guide*\.
- **Note**  
AWS Private CA immediately returns an ARN with a serial number when it receives the issue\-certificate command\. However, certificate processing happens asynchronously and can still fail\. If this happens, a get\-certificate command using the new ARN will also fail\.
- **Note**  
It is also possible to create a private CA that passes custom attributes to each certificate it issues\.


## Retrieving a private certificate

- **Note**  
If you want to revoke a certificate, you can use the get\-certificate command to retrieve the serial number in hexadecimal format\. You can also create an audit report to retrieve the hex serial number\. For more information, see [Using audit reports with your private CA](PcaAuditReport.md)\.


## Revoking a private certificate

- **Note**  
[Cross\-account](pca-resource-sharing.md) certificate issuers need additional permissions to revoke the certificates that they issue; otherwise, the CA owner must perform revocation\. To enable revocation by cross\-account issuers, the CA administrator must create two RAM shares, both pointing at the same CA:  
A share with the `AWSRAMRevokeCertificateCertificateAuthority` permission\.
A share with the `AWSRAMDefaultPermissionCertificateAuthority` permission\.


## Certificate templates

- **Note**  
AWS Certificate Manager \(ACM\) users with cross\-account shared access to a private CA can issue managed certificates that are signed by the CA\. Cross\-account issuers are constrained by a resource\-based policy and have access only to the following end\-entity certificate templates:  
[EndEntityCertificate/V1](#EndEntityCertificate-V1)
[EndEntityClientAuthCertificate/V1](#EndEntityClientAuthCertificate-V1)
[EndEntityServerAuthCertificate/V1](#EndEntityServerAuthCertificate-V1)
[BlankEndEntityCertificate\_APIPassthrough/V1](#BlankEndEntityCertificate_APIPassthrough)
[BlankEndEntityCertificate\_APICSRPassthrough/V1](#BlankEndEntityCertificate_APICSRPassthrough)
[SubordinateCACertificate\_PathLen0/V1](#SubordinateCACertificate_PathLen0-V1)
For more information, see [Resource\-based policies](pca-rbp.md)\.
- **Note**  
For information about template ARNs in GovCloud regions, see [AWS Certificate Manager Private Certificate Authority](https://docs.aws.amazon.com/govcloud-us/latest/UserGuide/using-govcloud-arns.html#using-govcloud-arn-syntax-acmpca) in the *AWS GovCloud \(US\) User Guide*\.
- **Note**  
A CSR that contains custom additional extensions must be created outside of AWS Private CA\.
- **Note**  
A CSR that contains custom additional extensions must be created outside of AWS Private CA\.
- **Note**  
A CSR that contains custom additional extensions must be created outside of AWS Private CA\.
- **Note**  
A CSR that contains custom additional extensions must be created outside of AWS Private CA\.

