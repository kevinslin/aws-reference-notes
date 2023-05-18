---
id: Manage resources
title: Manage resources
created: 1683841041000
updated: 1683841041000
---
# Manage resources

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/ec2-image-builder-user-guide.git)
{% endhint %}

## Components

- **Note**  
When a component that is managed by Amazon reaches the end of its support lifespan, it is no longer maintained\. About four weeks before this occurs, any accounts that are using the component receive notification, and a list of the affected recipes in their account from their AWS Health Dashboard\. To learn more about AWS Health, see [AWS Health User Guide](https://docs.aws.amazon.com/health/latest/ug/)\.
- **Note**  
While AWSTOE allows you to define many phases in a component document, Image Builder has strict rules about what phases it runs, and during which stages it runs them\. For a component to run during the build stage, the component document must define at least one of these phases: `build` or `validate`\. For a component to run during the test stage, the component document must define the `test` phase, and no other phases\.  
Since Image Builder runs the stages independently, chaining references in AWSTOE documents cannot cross stage boundaries\. You cannot chain a value from a phase that runs in the build stage to a phase that runs in the test stage\. You can, however, define input parameters to the intended target, and pass in values through the command line\. For more information about setting component parameters in your Image Builder recipes, see [Manage AWSTOE component parameters with EC2 Image Builder](manage-component-parameters.md)\.
- **Tip**  
When you have many components to keep track of, tagging helps you to identify a specific component or version based on the tags you've assigned to it\. For more information about tagging your resources using Image Builder commands in the AWS CLI, see the [Tag resources](tag-resources.md) section of this guide\.


## Recipes

- **Tip**  
You can use Amazon managed components in your recipes, or you can develop your own custom components with the AWS Task Orchestrator and Executor \(AWSTOE\) application\. To get started, see [Get started with AWSTOE](toe-get-started.md)\.


## Images

- **Tip**  
When you have multiple resources of the same type, tagging helps you to identify a specific resource based on the tags you've assigned to it\. For more information about tagging your resources using Image Builder commands in the AWS CLI, see the [Tag resources](tag-resources.md) section of this guide\.


## Infrastructure configurations

- **Tip**  
When you have multiple resources of the same type, tagging helps you to identify a specific resource based on the tags you've assigned to it\. For more information about tagging your resources using Image Builder commands in the AWS CLI, see the [Tag resources](tag-resources.md) section of this guide\.


## Distribution settings

- **Tip**  
When you have multiple resources of the same type, tagging helps you to identify a specific resource based on the tags you've assigned to it\. For more information about tagging your resources using Image Builder commands in the AWS CLI, see the [Tag resources](tag-resources.md) section of this guide\.


## Import and export VM images

- **Note**  
You must include the `file://` notation at the beginning of the JSON file path\.
The path for the JSON file should follow the appropriate convention for the base operating system where you are running the command\. For example, Windows uses the backslash \(\\\) to refer to the directory path, and Linux uses the forward slash \(/\)\.


## Share resources

- **Note**  
To set the correct policies for sharing and unsharing a resource, the resource owner must have `imagebuilder:put*` permissions\.
- **Note**  
To unshare a component, image, or recipe, the consumer cannot have any dependencies on them\. The consumer must remove any dependencies on the shared resources before the owner can unshare them\.


## Delete resources

- **Tip**  
To prevent dependency errors when you delete resources, make sure to delete your resources in the following order:  
Image pipeline
Image recipe
All remaining resources
- **Important**  
Make sure there are no recipes that reference the component build version in any way before you delete it\. Failing to do so could cause pipeline failures\.

