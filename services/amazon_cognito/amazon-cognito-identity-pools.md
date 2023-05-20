---
id: Amazon Cognito identity pools
title: Amazon Cognito identity pools
created: 1683841041000
updated: 1683841041000
---
# Amazon Cognito identity pools

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-cognito-developer-guide.git)
{% endhint %}

## Getting started with identity pools

- **Important**  
Currently, you must configure Amazon Cognito identity pools in the original console, even if you have migrated to the new console for Amazon Cognito user pools\. From the new console, choose **Federated identities** to navigate to the identity pools console\.


## Using identity pools

- **Important**  
Currently, you must configure Amazon Cognito identity pools in the original console, even if you have migrated to the new console for Amazon Cognito user pools\. From the new console, choose **Federated identities** to navigate to the identity pools console\.


## Using role-based access control

- **Note**  
Lambda functions use resource\-based policy, where the policy is attached directly to the Lambda function itself\. When creating a rule that invokes a Lambda function, you do not pass a role, so the user creating the rule does not need the `iam:PassRole` permission\. For more information about Lambda function authorization, see [Manage Permissions: Using a Lambda Function Policy](https://docs.aws.amazon.com/lambda/latest/dg/intro-permission-model.html#intro-permission-model-access-policy)\.
- **Note**  
In the rule settings, custom attributes require the `custom:` prefix to distinguish them from standard attributes\.
- **Important**  
If the claim that you are mapping to a role can be modified by the end user, any end user can assume your role and set the policy accordingly\. Only map claims that cannot be directly set by the end user to roles with elevated permissions\. In an Amazon Cognito user pool, you can set per\-app read and write permissions for each user attribute\.
- **Important**  
If you set roles for groups in an Amazon Cognito user pool, those roles are passed through the user's ID token\. To use these roles, you must also set **Choose role from token** for the authenticated role selection for the identity pool\.  
You can use the **Role resolution** setting in the console and the `RoleMappings` parameter of the [SetIdentityPoolRoles](https://docs.aws.amazon.com/cognitoidentity/latest/APIReference/API_SetIdentityPoolRoles.html) API to specify what the default behavior is when the correct role cannot be determined from the token\.


## Getting credentials

- **Note**  
If you created your identity pool before February 2015, you must reassociate your roles with your identity pool in order to use the `AWS.CognitoIdentityCredentials` constructor without the roles as parameters\. To do so, open the [Amazon Cognito console](https://console.aws.amazon.com/cognito/home), choose **Manage identity pools**, select your identity pool, choose **Edit identity Pool**, specify your authenticated and unauthenticated roles, and save the changes\.
- **Note**  
 Do not call `getIdentityId()`, `refresh()`, or `getCredentials()` in the main thread of your application\. As of Android 3\.0 \(API Level 11\), your app will automatically fail and throw a [NetworkOnMainThreadException](https://developer.android.com/reference/android/os/NetworkOnMainThreadException.html) if you perform network I/O on the main application thread\. You must move your code to a background thread using `AsyncTask`\. For more information, consult the [Android documentation](https://developer.android.com/training/basics/network-ops/connecting.html#AsyncTask)\. You can also call `getCachedIdentityId()` to retrieve an ID, but only if one is already cached locally\. Otherwise, the method will return null\.
- **Note**  
 If you created your identity pool before February 2015, you must reassociate your roles with your identity pool in order to use this constructor without the roles as parameters\. To do so, open the [Amazon Cognito console](https://console.aws.amazon.com/cognito/home), choose **Manage identity pools**, select your identity pool, choose **Edit identity Pool**, specify your authenticated and unauthenticated roles, and save the changes\.
- **Note**  
 `getIdentityId` is an asynchronous call\. If an identity ID is already set on your provider, you can call `credentialsProvider.identityId` to retrieve that identity, which is cached locally\. However, if an identity ID is not set on your provider, calling `credentialsProvider.identityId` will return `nil`\. For more information, consult the [Amplify iOS SDK reference](https://github.com/aws-amplify/aws-sdk-ios)\.
- **Note**  
 If you created your identity pool before February 2015, you must reassociate your roles with your identity pool in order to use this constructor without the roles as parameters\. To do so, open the [Amazon Cognito console](https://console.aws.amazon.com/cognito/home), choose **Manage identity pools**, select your identity pool, choose **Edit identity Pool**, specify your authenticated and unauthenticated roles, and save the changes\.
- **Note**  
 `getIdentityId` is an asynchronous call\. If an identity ID is already set on your provider, you can call `credentialsProvider.identityId` to retrieve that identity, which is cached locally\. However, if an identity ID is not set on your provider, calling `credentialsProvider.identityId` will return `nil`\. For more information, consult the [Amplify iOS SDK reference](https://github.com/aws-amplify/aws-sdk-ios)\.
- **Note**  
 **Note:** If you created your identity pool before February 2015, you must reassociate your roles with your identity pool in order to use this constructor without the roles as parameters\. To do so, open the [Amazon Cognito console](https://console.aws.amazon.com/cognito/home), choose **Manage identity pools**, select your identity pool, choose **Edit identity Pool**, specify your authenticated and unauthenticated roles, and save the changes\.


## Identity pools external identity providers

- **Important**  
Currently, you must configure Amazon Cognito identity pools in the original console, even if you have migrated to the new console for Amazon Cognito user pools\. From the new console, choose **Federated identities** to navigate to the identity pools console\.


## Developer-authenticated identities

- **Important**  
Currently, you must configure Amazon Cognito identity pools in the original console, even if you have migrated to the new console for Amazon Cognito user pools\. From the new console, choose **Federated identities** to navigate to the identity pools console\.

