---
id: Working with access points
title: Working with access points
created: 1683841041000
updated: 1683841041000
---
# Working with access points

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Configuring IAM policies

- **Important**  
Adding an S3 access point to a bucket doesn't change the bucket's behavior when the bucket is accessed directly through the bucket's name or Amazon Resource Name \(ARN\)\. All existing operations against the bucket will continue to work as before\. Restrictions that you include in an access point policy apply only to requests made through that access point\.
- **Note**  
Permissions granted in an access point policy are effective only if the underlying bucket also allows the same access\. You can accomplish this in two ways:  
**\(Recommended\)** Delegate access control from the bucket to the access point, as described in [Delegating access control to access points](#access-points-delegating-control)\.
Add the same permissions contained in the access point policy to the underlying bucket's policy\. The Example 1 access point policy example demonstrates how to modify the underlying bucket policy to allow the necessary access\.
- **Note**  
For the access point policy to effectively grant access to *`Jane`*, the underlying bucket must also allow the same access to *`Jane`*\. You can delegate access control from the bucket to the access point as described in [Delegating access control to access points](#access-points-delegating-control)\. Or, you can add the following policy to the underlying bucket to grant the necessary permissions to Jane\. Note that the `Resource` entry differs between the access point and bucket policies\.


## Creating access points

- **Note**  
Because you might want to publicize your access point name so that other users can use the access point, avoid including sensitive information in the access point name\. Access point names are published in a publicly accessible database known as the Domain Name System \(DNS\)\.

