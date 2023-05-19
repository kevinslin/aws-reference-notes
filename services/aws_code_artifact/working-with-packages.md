---
id: Working with packages
title: Working with packages
created: 1683841041000
updated: 1683841041000
---
# Working with packages

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codeartifact-user-guide.git)
{% endhint %}

## Packages overview

- **Note**  
Published npm packages are limited to a maximum size less than 2 GB\.
- **Note**  
Importing a package version from a public repository typically takes longer than publishing\. For more information, see [External connection latency](external-connection-requesting-packages.md#external-connection-latency)\.


## List package names

- **Important**  
The value for the `--namespace` option should not include the leading `@`\. To search for the namespace `@types`, set the value to *types*\.
- **Note**  
The `--namespace` option filters by namespace prefix\. Any npm package with a scope that starts with the value passed to the `--namespace` option will be returned in the `list-packages` response\.
- **Note**  
The `--namespace` option filters by namespace prefix\. Any npm package with a scope that starts with the value passed to the `--namespace` option will be returned in the `list-packages` response\.


## Download package version assets

- **Note**  
To download assets from a scoped npm package, include the scope in the `--namespace` option\. The `@` symbol must be omitted when using `--namespace`\. For example, if the scope is `@types`, use `--namespace types`\.


## Copy packages between repositories

- **Note**  
Calling `put-repository-permissions-policy` will replace the current repository policy if one exists\. You can use the `get-repository-permissions-policy` command to see if a policy exists, for more information see [Read a policy](repo-policies.md#reading-a-policy)\. If a policy does exist, you may want to add these permissions to it instead of replacing it\.
- **Note**  
You must specify the `--versions` or the `--version-revisions` parameter with `copy-package-versions`\. You cannot specify both\.


## View and update package version details and dependencies

- **Note**  
CodeArtifact does not extract package version detail information from parent POM files\. The metadata for a given package version will only include information in the POM for that exact package version, not for the parent POM or any other POM referenced transitively using the POM `parent` tag\. This means that the output of `describe-package-version` will omit metadata \(such as license information\) for Maven package versions that rely on a `parent` reference to contain this metadata\.
- **Note**  
CodeArtifact does not support displaying readme files from Maven packages\.


## Update package version status

- **Note**  
The `—-versions` parameter must also be defined when using the `--version-revisions` parameter\.


## Editing package origin controls

- **Note**  
Packages that existed in CodeArtifact repositories prior to around May 2022 will have a default package origin controls of **Publish: ALLOW** and **Upstream: ALLOW**\. Package origin controls must be set manually for such packages\. The current default values have been set on new packages since that time, and started being enforced when the feature launched on July 14, 2022\. For more information about setting package origin controls, see [Editing package origin controls](#edit-package-origin-controls)\.

