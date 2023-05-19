---
id: Creating and Managing Search Domains
title: Creating and Managing Search Domains
created: 1683841041000
updated: 1683841041000
---
# Creating and Managing Search Domains

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cloudsearch-developer-guide.git)
{% endhint %}

## Creating a Search Domain

- **Note**  
Amazon CloudSearch domains in different regions are entirely independent\. For example, if you create a search domain called *my\-domain* in us\-east\-1, and another domain called *my\-domain* in eu\-west\-1, they are completely independent and do not share any data\.
- **Important**  
By default, access to a new domain's document and search endpoints is blocked for all IP addresses\. You must configure access policies for the domain to be able to submit search requests to the domain's search endpoint and upload data from the command line or through the domain's document endpoint\. You can upload documents and search the domain through the Amazon CloudSearch console without configuring access policies\.
- **Important**  
Once a domain's endpoints are active, they remain the same for the life of the domain\. You should cache the endpoints—there's no need to query for the endpoint before submitting a document or search service request and doing so is likely to result in your requests being throttled\.


## Configuring Access

- **Important**  
To enable authentication, Amazon CloudSearch requests must be signed with an access key\. The only exception is if you allow anonymous access to a domain's upload, search, or suggest services\. For more information, see [Signing Requests](what-is-cloudsearch.md#signing-requests)\.
- **Important**  
When specifying an ARN for a domain created with the 2011\-02\-01 API, you must use the former Amazon CloudSearch service name, `cs`\. For example, `arn:aws:cs:us-east-1:111122223333:domain/movies`\. If you need to define policies that configure access for both 2011 and 2013 domains, make sure to specify the correct ARN format for each domain\. For more information, see [Configuration Service Access Policies Not Working](troubleshooting.md#troubleshooting-configuration-access-policies)\.
- **Important**  
To configure resource\-based policies for Amazon CloudSearch, you must have permission to use the `cloudsearch:UpdateServiceAccessPolicies` action\.
- **Important**  
Allowing anonymous access from selected IP addresses is inherently less secure than requiring user credentials to access your search domains\. We recommend against allowing anonymous access even if it is permitted only from select IP addresses\. If you currently allow anonymous access, you should upgrade your applications to submit signed requests and control access by configuring user\-based or resource\-based policies\.
- **Important**  
Allowing public access to a search domain means you have no control over the volume of requests submitted to the domain\. Malicious users could flood the domain with requests, impacting legitimate users as well as your operating costs\.


## Configuring Scaling Options

- **Note**  
The automatic scaling progression is based on the instance type's available disk space\. The `search.small` and `search.medium` instance types have the same amount of disk space, so both scale to `search.large`\.
- **Important**  
When you specify `--scaling-parameters`, Amazon CloudSearch treats unspecified options as "reset to default" rather than "leave as\-is\."  
For example, if you specify `--scaling-parameters DesiredInstanceType=search.xlarge` in a command and then `--scaling-parameters DesiredReplicationCount=2` in a subsequent command, Amazon CloudSearch resets `DesiredInstanceType` to its default value during the second command\.  
If you want the change from the first command to persist, you must specify it again in all subsequent commands: `--scaling-parameters DesiredInstanceType=search.xlarge,DesiredReplicationCount=2`\.


## Configuring Availability Options

- **Important**  
If your domain is running on a single search instance, enabling the Multi\-AZ option adds a second search instance in a different availability zone, which doubles the cost of running your domain\. Similarly, if your index is split across multiple partitions, a new instance is deployed in the second Availability Zone for each partition\. Additional replicas are added to ensure that either Availability Zone has enough capacity to handle all of your traffic—when Multi\-AZ is enabled, your domain will have at least one replica of each index partition\. If you set the desired number of replicas and enable the Multi\-AZ option, Amazon CloudSearch ensures that you have at least that many replicas available in total across the two availability zones\. You can monitor the number of instances being used for your domain from the domain dashboard\.


## Tagging Amazon CloudSearch Domains

- **Note**  
Tags are cached for authorization purposes\. Because of this, additions and updates to tags on Amazon CloudSearch domains might take several minutes before they are available\.

