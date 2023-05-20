---
id: Identities
title: Identities
created: 1683841041000
updated: 1683841041000
---
# Identities

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/iam-user-guide.git)
{% endhint %}

## Users

- **Important**  
 IAM [best practices](best-practices.md) recommend that you require human users to use federation with an identity provider to access AWS using temporary credentials instead of using IAM users with long\-term credentials\.
- **Important**  
If you found this page because you are looking for information about the Product Advertising API to sell Amazon products on your website, see the [Product Advertising API 5\.0 Documentation](https://webservices.amazon.com/paapi5/documentation/)\.


## Roles

- **Note**  
When you first create your AWS account, no roles are created by default\. As you add services to your account, they may add service\-linked roles to support their use cases\.  
  A service\-linked role is a type of service role that is linked to an AWS service\. The service can assume the role to perform an action on your behalf\. Service\-linked roles appear in your AWS account and are owned by the service\. An IAM administrator can view, but not edit the permissions for service\-linked roles\.   
Before you can delete service\-linked roles you must first delete their related resources\. This protects your resources because you can't inadvertently remove permission to access the resources\.  
For information about which services support using service\-linked roles, see [AWS services that work with IAM](reference_aws-services-that-work-with-iam.md) and look for the services that have **Yes **in the **Service\-Linked Role** column\. Choose a **Yes** with a link to view the service\-linked role documentation for that service\.


## Tagging IAM resources

- **Note**  
If your account is a member of AWS Organizations, see [Tag policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_tag-policies.html) in the Organizations user guide to learn more about using tags in Organizations\.

