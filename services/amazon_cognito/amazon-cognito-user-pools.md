---
id: Amazon Cognito user pools
title: Amazon Cognito user pools
created: 1683841041000
updated: 1683841041000
---
# Amazon Cognito user pools

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cognito-developer-guide.git)
{% endhint %}

## Updating a user pool

- **Important**  
If you don't provide values for existing parameters, Amazon Cognito sets them to default values\. For example, when you have existing `LambdaConfig` and you submit an `UpdateUserPool` with an empty `LambdaConfig`, you delete the assignment of all Lambda functions to user pool triggers\. Plan accordingly when you want to automate changes to your user pool configuration\.


## Using the hosted UI

- **Note**  
The Amazon Cognito hosted UI does not support the custom authentication flow\.


## Using Lambda triggers

- **Note**  
Federated users can use the Amazon Cognito hosted UI to sign in, or you can generate a request to the [Authorize endpoint](authorization-endpoint.md) that silently redirects them to their identity provider sign\-in page\. You can't sign in federated users with the Amazon Cognito native API\.


## Using Amazon Pinpoint analytics

- **Note**  
Amazon Pinpoint isn't available in Europe \(Milan\) and Middle East \(Bahrain\)\. Amazon Cognito user pools in these Regions don't support analytics\.
- **Note**  
For all AWS Regions except those in the preceding table, Amazon Cognito can only use an Amazon Pinpoint project in the same Region as your user pool\. If Amazon Pinpoint isn't available in the Region where you built your user pool, and it's not listed in the table, then Amazon Cognito doesn't support Amazon Pinpoint analytics in that Region\. For detailed AWS Region information, see [Amazon Pinpoint endpoints and quotas](https://docs.aws.amazon.com/general/latest/gr/pinpoint.html)\.
- **Note**  
Amazon Cognito supports in\-Region integrations when you use `ApplicationArn`


## Email settings

- **Note**  
In the AWS Management Console, you can only use Amazon SES resources in the same Region after you have switched to the new Amazon Cognito console experience\.
- **Note**  
You can't share the resources that you create in these steps across AWS accounts\. For example, you can't configure a user pool in one account, and then use it with an Amazon SES email address in a different account\. If you use Amazon Cognito in multiple accounts, repeat these steps for each account\.
- **Note**  
You can only configure a FROM address in a verified domain using the AWS CLI or the Amazon Cognito API\.


## SMS message settings

- **Note**  
In the AWS Management Console, you can only change the Region for SMS resources after you have switched to the new Amazon Cognito console experience\.
- **Note**  
Amazon SNS limits the number of destination phone numbers that you can verify while you are in the SMS sandbox\. See [SMS sandbox](https://docs.aws.amazon.com/sns/latest/dg/sns-sms-sandbox.html) in the *Amazon Simple Notification Service Developer Guide*\.


## Using tokens

- **Important**  
Best practice is to secure all tokens in transit and storage in the context of your application\. Tokens can contain personally\-identifying information about your users, and information about the security model that you use for your user pool\.

