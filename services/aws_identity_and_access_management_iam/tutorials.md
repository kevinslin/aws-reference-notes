---
id: Tutorials
title: Tutorials
created: 1683841041000
updated: 1683841041000
---
# Tutorials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/iam-user-guide.git)
{% endhint %}

## Delegate access to the billing console

- **Note**  
If you [create a member account](https://docs.aws.amazon.com/cli/latest/reference/organizations/create-account.html) using AWS Organizations, this feature is enabled by default\.


## Delegate access across AWS accounts using roles

- **Note**  
IAM roles and resource\-based policies delegate access across accounts only within a single partition\. For example, assume that you have an account in US West \(N\. California\) in the standard `aws` partition\. You also have an account in China \(Beijing\) in the `aws-cn` partition\. You can't use an Amazon S3 resource\-based policy in your account in China \(Beijing\) to allow access for users in your standard `aws` account\.
- **Important**  
You can switch to a role only after you sign in as an IAM user or a federated user\. Additionally, if you launch an Amazon EC2 instance to run an application, the application can assume a role through its instance profile\. You cannot switch to a role when you sign in as the AWS account root user\.
- **Important**  
Switching roles using the AWS Management Console only works with accounts that do not require an `ExternalId`\. For example, assume that you grant access to your account to a third party and require an `ExternalId` in a `Condition` element in your permissions policy\. In that case, the third party can access your account only by using the AWS API or a command line tool\. The third party cannot use the console because it cannot supply a value for `ExternalId`\. For more information about this scenario, see [How to use an external ID when granting access to your AWS resources to a third party](id_roles_create_for-user_externalid.md), and [How to Enable Cross\-Account Access to the AWS Management Console](http://aws.amazon.com/blogs/security/how-to-enable-cross-account-access-to-the-aws-management-console) in the AWS Security Blog\.
- **Note**  
David's default environment uses the `David` user credentials from his default profile that he created with the `aws configure` command\. For more information, see [Configuring the AWS Command Line Interface](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html#cli-quick-configuration) in the *AWS Command Line Interface User Guide*\.


## Use attribute-based access control (ABAC)

- **Note**  
You must pass a single value for each session tag\. AWS Security Token Service does not support multi\-valued session tags\.
- **Important**  
This policy uses a strategy to allow all actions for a service, but explicitly deny permissions\-altering actions\. Denying an action overrides any other policy that allows the principal to perform that action\. This can have unintended results\. As a best practice, use explicit denies only when there is no circumstance that should allow that action\. Otherwise, allow a list of individual actions, and the unwanted actions are denied by default\.
- **Note**  
You added policies that allow actions only under specific conditions\. If you apply a different policy to your users or roles that has broader permissions, then the actions might not be limited to require tagging\. For example, if you give a user full administrative permissions using the `AdministratorAccess` AWS managed policy, then these policies don't restrict that access\. For more information about how permissions are determined when multiple policies are involved, see [Determining whether a request is allowed or denied within an account](reference_policies_evaluation-logic.md#policy-eval-denyallow)\.

