---
id: Managing permissions in AWS RAM
title: Managing permissions in AWS RAM
created: 1683841041000
updated: 1683841041000
---
# Managing permissions in AWS RAM

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-resource-access-manager-user-guide.git)
{% endhint %}

## Updating managed permission versions

- **Note**  
You can attach only the default version, and you can't revert to another version\.  
For customer managed permissions, after you update the permissions to the default version, you can't apply another version to a resource share unless you first set that other version as the default\. For example, if you updated a permission to the default version and then found an error that you wanted to roll back, you could designate the previous version as the default\. Alternatively, you could create a different new version and then designate that as the default\. After you performed one of those options, you would then update your resource shares to use what is now the default version\.

