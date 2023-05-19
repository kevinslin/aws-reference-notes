---
id: Authentication and access credentials
title: Authentication and access credentials
created: 1683841041000
updated: 1683841041000
---
# Authentication and access credentials

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cli-user-guide.git)
{% endhint %}

## IAM Identity Center authentication

- **Note**  
If you specify `default` as the profile name, this profile becomes the one used whenever you run an AWS CLI command and do not specify a profile name\.
- **Note**  
You can also run an AWS CLI command using the specified profile\. If you are not currently logged in to the AWS access portal, it starts the login process for you automatically, just as if you had manually ran the command `aws sso login` command\.


## IAM roles

- **Note**  
When you specify a profile that uses an IAM role, the AWS CLI makes the appropriate calls to retrieve temporary credentials\. These credentials are stored in `~/.aws/cli/cache`\. Subsequent AWS CLI commands that specify the same profile use the cached temporary credentials until they expire\. At that point, the AWS CLI automatically refreshes the credentials\.
- **Note**  
These environment variables currently apply only to the assume role with web identity provider\. They don't apply to the general assume role provider configuration\.


## External credentials

- **Note**  
As of this writing, the `Version` key must be set to `1`\. This might increment over time as the structure evolves\.
- **Note**  
The AWS CLI does ***not*** cache external process credentials the way it does assume\-role credentials\. If caching is required, you must implement it in the external process\.

