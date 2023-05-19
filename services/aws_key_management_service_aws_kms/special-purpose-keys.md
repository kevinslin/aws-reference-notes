---
id: Special-purpose keys
title: Special-purpose keys
created: 1683841041000
updated: 1683841041000
---
# Special-purpose keys

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-kms-developer-guide.git)
{% endhint %}

## HMAC keys

- **Tip**  
Best practices recommend that you limit the time during which any signing mechanism, including an HMAC, is effective\. This deters an attack where the actor uses a signed message to establish validity repeatedly or long after the message is superseded\. HMAC tags do not include a timestamp, but you can include a timestamp in the token or message to help you detect when its time to refresh the HMAC\.


## Imported key material

- **Note**  
AWS KMS does not support decrypting any AWS KMS ciphertext outside of AWS KMS, even if the ciphertext was encrypted under a KMS key with imported key material\. AWS KMS does not publish the ciphertext format this task requires, and the format might change without notice\.

