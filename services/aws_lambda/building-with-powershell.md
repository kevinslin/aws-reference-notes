---
id: Building with PowerShell
title: Building with PowerShell
created: 1683841041000
updated: 1683841041000
---
# Building with PowerShell
{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}
## Handler

- **Note**  
You're required to use the `#Requires` statement within your PowerShell scripts to indicate the modules that your scripts depend on\. This statement performs two important tasks\. 1\) It communicates to other developers which modules the script uses, and 2\) it identifies the dependent modules that AWS PowerShell tools need to package with the script, as part of the deployment\. For more information about the `#Requires` statement in PowerShell, see [ About requires](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-6)\. For more information about PowerShell deployment packages, see [Deploy PowerShell Lambda functions with \.zip file archives](powershell-package.md)\.  
When your PowerShell Lambda function uses the AWS PowerShell cmdlets, be sure to set a `#Requires` statement that references the `AWSPowerShell.NetCore` module, which supports PowerShell Core—and not the `AWSPowerShell` module, which only supports Windows PowerShell\. Also, be sure to use version 3\.3\.270\.0 or newer of `AWSPowerShell.NetCore` which optimizes the cmdlet import process\. If you use an older version, you'll experience longer cold starts\. For more information, see [AWS Tools for PowerShell](http://aws.amazon.com/powershell/?track=sdk)\.

