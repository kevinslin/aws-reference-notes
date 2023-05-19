---
id: Setting up
title: Setting up
created: 1683841041000
updated: 1683841041000
---
# Setting up

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-transfer-user-guide.git)
{% endhint %}

## Create an Amazon S3 bucket

- **Note**  
You don't have to use a server and Amazon S3 bucket that are in the same AWS Region, but we recommend this as a best practice\.
- **Note**  
 You can use Amazon S3 Object Lock to prevent objects from being overwritten for a fixed amount of time or indefinitely\. This works the same way with Transfer Family as with other services\. If an object exists and is protected, writing to that file or deleting it is not allowed\. For more details on Amazon S3 Object Lock, see [Using Amazon S3 Object Lock](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/object-lock.html) in the *Amazon Simple Storage Service User Guide*\.
- **Note**  
AWS Transfer Family does not currently support Amazon S3 Multi\-Region Access Points\.
- **Note**  
This policy does not allow for appending to a file\. That is, a user that is assigned to this policy cannot open files to add content to them, or to modify them\. Also, if your use case involves issuing a `HeadObject` call before uploading a file, this policy won't work for you\.


## Create an Amazon EFS file system

- **Note**  
When you use a Transfer Family server and an Amazon EFS file system, the server and the file system must be in the same AWS Region\.


## Create an IAM role and policy

- **Note**  
When you are creating a service\-managed Transfer Family user, you can select **Auto\-generate policy based on home folder**\. This is a useful shortcut if you want to limit user access to their own folders\. Also, you can view details about session policies and an example in [How session policies work](#session-policy)\. You can also find more information about session policies in [Session policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_session) in the *IAM User Guide*\.
- **Note**  
In the examples above, replace each *user input placeholder* with your own information\.
- **Note**  
 The maximum length of a session policy is 2048 characters\. For more details, see the [Policy request parameter](https://docs.aws.amazon.com/transfer/latest/userguide/API_CreateUser.html#API_CreateUser_RequestSyntax) for the `CreateUser` action in the *API reference*\.
- **Note**  
 If your Amazon S3 bucket is encrypted using AWS Key Management Service \(AWS KMS\), you must specify additional permissions in your policy\. For details, see [Data encryption](encryption-at-rest.md)\. Additionally, you can see more information about [session policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_session.html) in the *IAM User Guide*\.
- **Note**  
In the preceding policy, it is assumed that users have their home directories set to include a trailing slash, to signify that it is a directory\. If, on the other hand, you set a user's `HomeDirectory` without the trailing slash, then you should include it as part of your policy\.
- **Note**  
 If you are using Logical directories—that is, the user's `homeDirectoryType` is `LOGICAL`—these policy parameters \(`HomeBucket`, `HomeDirectory`, and `HomeFolder`\) are not supported\.
- **Note**  
In the following example, replace *bucket\_name* with the name of your S3 bucket\.  
Also, note that the `GetObjectACL` and `PutObjectACL` statements are only required if you are doing Cross Account Access\. That is, your Transfer Family server needs to access a bucket in a different account\.
- **Note**  
In addition to the policy, you must also make sure your POSIX file permissions are granting the appropriate access\. For more information, see [Working with users, groups, and permissions at the Network File System \(NFS\) Level](https://docs.aws.amazon.com/efs/latest/ug/accessing-fs-nfs-permissions.html) in the *Amazon Elastic File System User Guide*\.
- **Note**  
In the following examples, replace *region* with your region, *account\-id* with the account the file is in, and *file\-system\-id* with the ID of your Amazon Elastic File System \(Amazon EFS\)\.

