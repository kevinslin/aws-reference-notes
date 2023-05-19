---
id: Working with repositories
title: Working with repositories
created: 1683841041000
updated: 1683841041000
---
# Working with repositories

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codeartifact-user-guide.git)
{% endhint %}

## Create a repository

- **Note**  
After you create a repository, you cannot change its name, associated AWS account, or domain\.
- **Note**  
To create a repository with an upstream, you must have permission for the `AssociateWithDownstreamRepository` action on the upstream repository\.


## View or modify a repository configuration

- **Note**  
After you create a repository, you cannot change its name, associated AWS account, or domain\.
- **Note**  
To add an upstream repository, you must have permission for the `AssociateWithDownstreamRepository` action on the upstream repository\.


## Repository policies

- **Note**  
The `codeartifact:ReadFromRepository` action can only be used on a repository resource\. You cannot put a package's Amazon Resource Name \(ARN\) as a resource with `codeartifact:ReadFromRepository` as the action to allow read access to a subset of packages in a repository\. A given principal can either read all the packages in a repository or none of them\.
- **Note**  
 You cannot grant permissions to another AWS account to update the resource policy on a repository using a resource policy, since the resource policy is ignored when calling put\-repository\-permissions\-policy\.
- **Important**  
To grant permission to publish Maven and NuGet package versions, add the following permissions in addition to `codeartifact:PublishPackageVersion`\.  
NuGet: `codeartifact:ReadFromRepository` and specify the repository resource
Maven: `codeartifact:PutPackageMetadata`


## Tag a repository

- **Note**  
To get the ARN of the repository, run the `describe-repository` command:
- **Note**  
To get the ARN of the repository, run the `describe-repository` command:
- **Note**  
To get the ARN of the repository, run the `describe-repository` command:
- **Note**  
If you delete a repository, all tag associations are removed from the deleted repository\. You do not have to remove tags before you delete a repository\.
- **Note**  
To get the ARN of the repository, run the `describe-repository` command:

