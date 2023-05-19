---
id: Application assignments
title: Application assignments
created: 1683841041000
updated: 1683841041000
---
# Application assignments

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-single-sign-on-user-guide.git)
{% endhint %}

## Cloud applications

- **Note**  
AWS Support engineers can assist customers who have Business and Enterprise support plans with some integration tasks that involve third\-party software\. For a current list of supported platforms and applications, see [Third\-Party Software Support](https://aws.amazon.com/premiumsupport/faqs/#what3rdParty) on the *AWS Support Features* page\.


## Assign user access to applications

- **Note**  
To help simplify administration of access permissions, we recommend that you assign access directly to groups rather than to individual users\. With groups you can grant or deny permissions to groups of users, rather than having to apply those permissions to each individual\. If a user moves to a different organization, you simply move that user to a different group\. The user then automatically receives the permissions that are needed for the new organization\.
When assigning user access to applications, IAM Identity Center does not currently support users being added to nested groups\. If a user is added to a nested group, they may receive a “You do not have any applications” message during sign\-in\. Assignments must be made against the immediate group the user is a member of\.

