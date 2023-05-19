---
id: Working with VPC endpoints
title: Working with VPC endpoints
created: 1683841041000
updated: 1683841041000
---
# Working with VPC endpoints

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codeartifact-user-guide.git)
{% endhint %}

## Create VPC endpoints

- **Note**  
 When you create a `codeartifact.repositories` endpoint, you must create a private DNS hostname using the `--private-dns-enabled` option\. However, because multiple private DNS hostnames are not currently supported for the `codeartifact.api` and `codeartifact.repositories` endpoints, use the `--no-private-dns-enabled` option for `codeartifact.api`\. If you can't or do not want to create a private DNS hostname when you create the `codeartifact.repositories` endpoint, you must follow an extra configuration step to use your package manager with CodeArtifact from a VPC\. See [Use the `codeartifact.repositories` endpoint without private DNS](use-codeartifact-from-vpc.md#use-codeartifact-from-vpc-no-private-dns) for more information\.

