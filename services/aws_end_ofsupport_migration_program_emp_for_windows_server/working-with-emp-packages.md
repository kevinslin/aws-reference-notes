---
id: Working with EMP packages
title: Working with EMP packages
created: 1683841041000
updated: 1683841041000
---
# Working with EMP packages

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/emp-user-guide.git)
{% endhint %}

## Compatibility package features

- **Note**  
This feature, when enabled, causes the printer driver host for 32\-bit applications \(`SPLWOW64.exe`\) to fail, and must be excluded if the packaged application launches it\.
- **Note**  
Apply the Microsoft server naming conventions described at [https://docs\.microsoft\.com/en\-us/troubleshoot/windows\-server/identity/naming\-conventions\-for\-computer\-domain\-site\-ou](https://docs.microsoft.com/en-us/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou)\. These are the only naming conventions supported\.


## Edit, upgrade, and maintain packages

- **Important**  
You must use the Package Editor to update an EMP package on the same architecture on which the original package was created\. For example, if the package was created on an x86 machine, then the Editor must update the package on an x86 machine\.


## Update a deployed package

- **Important**  
If you attempt to use the `/deploydir` switch when a package has already been deployed, a `Failed to deploy' exit code -1` error will be returned\. The `/update` switch must be used to update the package to the latest version, or the `/uninstall` switch must be used to remove the package first\.
- **Note**  
The `/update` switch preserves any values that appear in the registry that are not specified in the source file\. If the file type associations source file \(`FileAssociations.xml`\) in the new package is different from the one in the currently deployed package, `/update` deletes the registry values that do not appear in `FileAssociations.xml` and updates values and types that have changed\.


## Uninstall a package

- **Note**  
If you run this command from the deployed location, the uninstall will be incomplete\. Verify that the package is uninstalled from the correct source path\.


## Enable logging

- **Note**  
`LocalAppData` resolves to a special location for the `SYSTEM` account: `C:\Windows\System32\config\systemprofile\AppData\Local`\.


## Enable out-of-process COM

- **Note**  
The `COMVirtualization` feature is not required if the application uses in\-process COM objects\. Applications that use in\-process COM objects behave as expected without enabling the feature\.


## Exclude or detach a process

- **Important**  
The virtualization and redirection engine of the package will detach from the parent process once virtualization is complete\. Any child processes will not be virtualized, and the detached process will not benefit from `DEPOptOut` or `HandleInvalidHandle`, even if these features are enabled\.

