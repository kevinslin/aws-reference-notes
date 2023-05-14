---
id: Working with Multi-Region Access Points
title: Working with Multi-Region Access Points
created: 1683841041000
updated: 1683841041000
---
# Working with Multi-Region Access Points

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Creating Multi-Region Access Points

- **Note**  
For an application or user to be able to access an object through a Multi\-Region Access Point, both of the following policies must permit the request:   
The access policy for the Multi\-Region Access Point
The access policy for the underlying bucket that contains the object
When the two policies are different, the more restrictive policy takes precedence\.   
To simplify permissions management for Multi\-Region Access Points, you can delegate access control from the bucket to the Multi\-Region Access Point\. For more information, see [Multi\-Region Access Point policy examples](MultiRegionAccessPointPermissions.md#MultiRegionAccessPointPolicyExamples)\.


## Using Multi-Region Access Points

- **Note**  
The Multi\-Region Access Point alias and ARN cannot be used interchangeably\.

