---
id: Managing keys
title: Managing keys
created: 1683841041000
updated: 1683841041000
---
# Managing keys

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-kms-developer-guide.git)
{% endhint %}

## Creating keys

- **Note**  
Symmetric KMS keys are now called *symmetric encryption* KMS keys\. AWS KMS supports two kinds of symmetric KMS keys, [symmetric encryption KMS keys](concepts.md#symmetric-cmks) \(the default type\) and [HMAC KMS keys](concepts.md#hmac-key-concept), which are also symmetric keys\.
- **Note**  
Be cautious when giving principals permission to manage tags and aliases\. Changing a tag or alias can allow or deny permission to the customer managed key\. For details, see [ABAC for AWS KMS](abac.md)\.


## Enabling and disabling keys

- **Note**  
AWS KMS does not rotate the key material of customer managed keys while they are disabled\. For more information, see [How automatic key rotation works](rotate-keys.md#rotate-keys-how-it-works)\.


## Rotating keys

- **Note**  
The rotation interval for AWS managed keys changed in May 2022\. For details, see [AWS managed keys](#rotate-aws-managed-keys)\.
- **Note**  
When you begin using the new KMS key, be sure to keep the original KMS key enabled so that AWS KMS can decrypt data that the original KMS key encrypted\.
- **Note**  
Aliases that point to the latest version of a manually rotated KMS key are a good solution for the [DescribeKey](https://docs.aws.amazon.com/kms/latest/APIReference/API_DescribeKey.html), [Encrypt](https://docs.aws.amazon.com/kms/latest/APIReference/API_Encrypt.html), [GenerateDataKey](https://docs.aws.amazon.com/kms/latest/APIReference/API_GenerateDataKey.html), [GenerateDataKeyPair](https://docs.aws.amazon.com/kms/latest/APIReference/API_GenerateDataKeyPair.html), [GenerateMac](https://docs.aws.amazon.com/kms/latest/APIReference/API_GenerateMac.html), and [Sign](https://docs.aws.amazon.com/kms/latest/APIReference/API_Sign.html) operations\. Aliases are not permitted in operations that manage KMS keys, such as [DisableKey](https://docs.aws.amazon.com/kms/latest/APIReference/API_DisableKey.html) or [ScheduleKeyDeletion](https://docs.aws.amazon.com/kms/latest/APIReference/API_ScheduleKeyDeletion.html)\.  
When calling the [Decrypt](https://docs.aws.amazon.com/kms/latest/APIReference/API_Decrypt.html) operation on manually rotated symmetric encryption KMS keys, omit the `KeyId` parameter from the command\. AWS KMS automatically uses the KMS key that encrypted the ciphertext\.  
The `KeyId` parameter is required when calling `Decrypt` or [Verify](https://docs.aws.amazon.com/kms/latest/APIReference/API_Verify.html) with an asymmetric KMS key, or calling [VerifyMac](https://docs.aws.amazon.com/kms/latest/APIReference/API_VerifyMac.html) with an HMAC KMS key\. These requests fail when the value of the `KeyId` parameter is an alias that no longer points to the KMS key that performed the cryptographic operation, such as when a key is manually rotated\. To avoid this error, you must track and specify the correct KMS key for each operation\.


## Using CloudFormation templates

- **Important**  
If you change the value of the `KeyUsage`, `KeySpec`, or `MultiRegion` property of an existing KMS key, the existing KMS key is scheduled for deletion and a new KMS key is created with the specified value\.  
While scheduled for deletion, the existing KMS key becomes unusable\. If you don't cancel the scheduled deletion of the existing KMS key outside of AWS CloudFormation, all data encrypted under the existing KMS key becomes unrecoverable when the KMS key is deleted\.


## Deleting keys

- **Note**  
If you [close or delete your AWS account](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/close-account.html), your KMS keys become inaccessible and you are no longer billed for them\. You do not need to schedule deletion of your KMS keys separate from closing the account\.


## Key state reference

- **Note**  
You might need to scroll horizontally or vertically to see all of the data in this table\.

