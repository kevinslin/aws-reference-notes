---
id: Walkthroughs
title: Walkthroughs
created: 1683841041000
updated: 1683841041000
---
# Walkthroughs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-control-tower-guide.git)
{% endhint %}

## Walkthrough: Automate Account Provisioning in AWS Control Tower by Service Catalog APIs

- **Note**  
You also can adapt this approach for automating account updates, by calling the [https://docs.aws.amazon.com/servicecatalog/latest/dg/API_UpdateProvisionedProduct.html](https://docs.aws.amazon.com/servicecatalog/latest/dg/API_UpdateProvisionedProduct.html) API of AWS Service Catalog for each account\. You can write a script to update the accounts, one by one\.
- **Note**  
Notice that the format of the input string for the value of `ManagedOrganizationalUnit` has changed from `OU_NAME` to `OU_NAME (OU_ID)`\. The video that follows does not mention this change\.


## Walkthrough: Configure AWS Control Tower Without a VPC

- **Important**  
If you provision Account Factory accounts with VPC internet access settings enabled, that Account Factory setting overrides the control [Disallow internet access for an Amazon VPC instance managed by a customer](data-residency-controls.md#disallow-vpc-internet-access)\. To avoid enabling internet access for newly provisioned accounts, you must change the setting in Account Factory\.


## Walkthrough: Decommission an AWS Control Tower Landing Zone

- **Important**  
 We strongly recommend that you perform this decommissioning process only if you intend to stop using your landing zone\. It is not possible to re\-create your existing landing zone after you've decommissioned it\.

