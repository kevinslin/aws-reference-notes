---
id: Using npm
title: Using npm
created: 1683841041000
updated: 1683841041000
---
# Using npm

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codeartifact-user-guide.git)
{% endhint %}

## Configure and use npm

- **Note**  
If you are accessing a repository in a domain that you own, you don't need to include `--domain-owner`\. For more information, see [Cross\-account domains](domain-overview.md#domain-overview-cross-account)\.
- **Important**  
The registry URL must end with a forward slash \(/\)\. Otherwise, you cannot connect to the repository\.


## Configure and use Yarn

- **Note**  
`Yarn 1.X` reads and uses information from your npm configuration file \(\.npmrc\), while `Yarn 2.X` does not\. The configuration for `Yarn 2.X` must be defined in the \.yarnrc\.yml file\.


## Support for npm-compatible package managers

- **Note**  
We recommend using Yarn 2\.x with CodeArtifact\. Yarn 1\.x does not have HTTP retries, which means it is more susceptible to intermittent service faults which result in 500\-level status codes or errors\. There is no way to configure a different retry strategy for Yarn 1\.x, but this has been added in Yarn 2\.x\. You can use Yarn 1\.x, but you may need to add higher\-level retries in build scripts\. For example, running your yarn command in a loop so that it will retry if downloading packages fails\.

