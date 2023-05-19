---
id: Monitoring data with web portals
title: Monitoring data with web portals
created: 1683841041000
updated: 1683841041000
---
# Monitoring data with web portals

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-sitewise-user-guide.git)
{% endhint %}

## Getting started

- **Important**  <a name="iam-portal-user-permissions"></a>
IAM users or roles must have the `iotsitewise:DescribePortal` permission to sign in to the portal\.
- **Note**  
If you use AWS SSO as your identity store, and you're signed in to your AWS Organizations management account, you can choose **Create user** to create an AWS SSO user\. AWS SSO sends the new user an email for them to set their password\. You can then assign the user to the portal as an administrator\. For more information, see [Manage identities in AWS SSO](https://docs.aws.amazon.com/singlesignon/latest/userguide/manage-your-identity-source-sso.html.html)\.
- **Note**  
Because only a portal administrator can create projects and assign assets to them, you should specify at least one portal administrator\.
- **Important**  <a name="iam-portal-user-permissions"></a>
IAM users or roles must have the `iotsitewise:DescribePortal` permission to sign in to the portal\.


## Enabling additional features

- **Important**  
You can't create external alarms in your portals\.
If you want to send alarm notifications, you must choose AWS SSO for the user authentication service\.
The alarm notifications feature isn't available in the China \(Beijing\) Region\.


## Administering your portals

- **Important**  <a name="iam-portal-user-permissions"></a>
IAM users or roles must have the `iotsitewise:DescribePortal` permission to sign in to the portal\.
- **Note**  
Your portal administrators and portal users might contact you through a portal's support email if they need you to add or remove a user\.
- **Important**  <a name="iam-portal-user-permissions"></a>
IAM users or roles must have the `iotsitewise:DescribePortal` permission to sign in to the portal\.
- **Note**  
You must first manually delete all dashboards and projects in a portal before you can delete a portal\. For more information, see [Deleting projects](https://docs.aws.amazon.com/iot-sitewise/latest/appguide/delete-projects) and [Deleting dashboards](https://docs.aws.amazon.com/iot-sitewise/latest/appguide/delete-dashboards) in the *SiteWise Monitor Application Guide*\.

