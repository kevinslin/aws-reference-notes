---
id: Planning a private CA
title: Planning a private CA
created: 1683841041000
updated: 1683841041000
---
# Planning a private CA

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-private-ca-user-guide.git)
{% endhint %}

## AWS account and CLI

- **Note**  
AWS Private CA is not available in the [AWS Free Tier](https://aws.amazon.com/free/)\.


## Designing a CA hierarchy

- **Note**  
Using a root CA to sign a subordinate certificate is a rare event that occurs in only a handful of circumstances:  
When the PKI is created
When a high\-level certificate authority needs to be replaced
When a certificate revocation list \(CRL\) or Online Certificate Status Protocol \(OCSP\) responder needs to be configured
Root and other high\-level CAs require highly secure operational processes and access\-control protocols\.
- **Note**  
AWS Private CA limits the certification path to five levels\.


## Managing the CA lifecycle

- **Note**  
Private certificates issued through ACM cannot be renewed if you replace the CA\. If you use ACM for issuance and renewal, you must re\-issue the CA certificate to extend the lifetime of the CA\.
- **Note**  
We recommend replacing an expiring CA rather than reissuing its certificate because of the security advantages gained by rotating to a new key pair\.


## Revocation

- **Note**  
If you create your CA without configuring revocation, you can always configure it later\. For more information, see [Updating your private CA](PCAUpdateCA.md)\.
- **Note**  
Both OCSP and CRLs exhibit some delay between revocation and the availability of the status change\.  
OCSP responses may take up to 60 minutes to reflect the new status when you revoke a certificate\. In general, OCSP tends to support faster distribution of revocation information because, unlike CRLs which can be cached by clients for days, OCSP responses are typically not cached by clients\.
A CRL is typically updated approximately 30 minutes after a certificate is revoked\. If for any reason a CRL update fails, AWS Private CA makes further attempts every 15 minutes\.


## CA modes

- **Note**  
AWS Private CA does not perform validity checks on root CA certificates\.
- **Note**  
AWS Certificate Manager cannot issue certificates signed by a private CA with short\-lived mode\.

