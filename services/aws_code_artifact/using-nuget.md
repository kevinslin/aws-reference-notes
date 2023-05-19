---
id: Using NuGet
title: Using NuGet
created: 1683841041000
updated: 1683841041000
---
# Using NuGet

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codeartifact-user-guide.git)
{% endhint %}

## Use CodeArtifact with Visual Studio

- **Note**  
 The AWS Toolkit for Visual Studio is not available for Visual Studio for Mac\.
- **Important**  
To use the credential provider, ensure that any existing AWS CodeArtifact credentials are cleared from your `nuget.config` file that may have been added manually or by running `aws codeartifact login` to configure NuGet previously\.


## Use CodeArtifact with nuget or dotnet

- **Important**  
To use the credential provider, ensure that any existing AWS CodeArtifact credentials are cleared from your `nuget.config` file that may have been added manually or by running `aws codeartifact login` to configure NuGet previously\.
- **Important**  
**Linux and MacOS users:** Because encryption is not supported on non\-Windows platforms, your fetched credentials will be stored as plain text in your configuration file\.
- **Note**  
To update an existing source, use the `dotnet nuget update source` command\.
- **Note**  
When a package is requested, the NuGet client caches which versions of that package exists\. Because of this behavior, an install may fail for a package that was requested before it was available\. To avoid this failure and successfully install a package that exists, you can either clear the NuGet cache ahead of an install with `nuget locals all --clear` or use the `--no-cache` option when running `nuget install` or `nuget restore`\.
- **Note**  
You can create a NuGet package if you do not have one to publish\. For more information, see [Package creation workflow](https://docs.microsoft.com/en-us/nuget/create-packages/overview-and-workflow) in the *Microsoft documentation*\.

