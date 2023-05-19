---
id: Tutorials and samples
title: Tutorials and samples
created: 1683841041000
updated: 1683841041000
---
# Tutorials and samples

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## AWS CLI and AWS CloudShell sample

- **Note**  
Bucket names must be unique across all of AWS, not just your AWS account\. The preceding suggested bucket name can help you come up with a unique bucket name\. If you get a message that contains the error `BucketAlreadyExists`, you must run the command again with a different bucket name\.


## AWS CodeCommit sample

- **Note**  
If you prefer working with Git through a visual interface, you can clone the remote repository and then add files using the [Git panel](source-control-gitpanel.md) feature that's available in the IDE\.
- **Note**  
To confirm you are saving this file in the correct directory, in the **Save As** dialog box, choose the `MyDemoCloud9Repo` folder, and be sure **Folder** displays `/MyDemoCloud9Repo`\.


## Amazon DynamoDB sample

- **Note**  
Throughout this sample, if you're using the aws\-shell, omit `aws` from each command that starts with `aws`\. To start the aws\-shell, run the ** `aws-shell` ** command\. To stop using the aws\-shell, run the ** `.exit` ** or ** `.quit` ** command\.
- **Note**  
Creating secondary indexes might result in additional charges to your AWS account\.


## AWS CDK sample

- **Note**  
The preceding command sets Node\.js 16\.17\.0 as the default version of Node\.js\. Alternatively, you can run the ** `nvm` ** command along with the ** `use` ** action instead of the ** `alias` ** action \(for example, ** `nvm use 16.17.0` **\)\. However, the ** `use` ** action causes that version of Node\.js to run only while the current terminal session is running\.
- **Note**  
If you run `cdk bootstrap` without specifying any options, the default AWS account and AWS Region are used\. You can also bootstrap a specific environment by specifying a profile and account/Region combination\. For example:


## LAMP sample

- **Important**  
Running the following commands disables incoming web traffic over port 80 for **all** EC2 environments and Amazon EC2 instances that are associated with the security group and network ACL for this environment\. This might result in unexpectedly disabling incoming web traffic over port 80 for EC2 environments and Amazon EC2 instances other than this one\.
- **Note**  
The following fifth through eighth commands remove existing rules in order to block the network ACL from allowing incoming web traffic over port 80\. If you have a default network ACL, which already allows all incoming traffic over all ports, then you can safely skip running those commands\. However, if you have a custom network ACL with existing rules that allow incoming web traffic over port 80 and you want to delete those rules, then you must run the first command followed by these fifth through eighth commands\.


## WordPress sample

- **Note**  
Creating this sample might result in charges to your AWS account\. These include possible charges for services such as Amazon Elastic Compute Cloud \(Amazon EC2\)\. For more information, see [Amazon EC2 Pricing](https://aws.amazon.com/ec2/pricing/)\.
- **Important**  
By default, all web pages that you access in the application preview tab of the AWS Cloud9 IDE automatically use the HTTPS protocol\. If a page's URI features the insecure `http` protocol, it's automatically replaced by `https`\. And you can't access the insecure content by manually changing `https` back to `http`\.  
For guidance on implementing HTTPS for your web site, see the [WordPress documentation](https://wordpress.org/support/article/https-for-wordpress/)\.


## Java sample

- **Important**  
If you're using an AWS Cloud9 development environment that's backed by an EC2 instance with 2 GiB or more of memory, we recommend that you activate enhanced Java support\. This provides access to productivity features such as code completion, linting for errors, context\-specific actions, and debugging options such as breakpoints and stepping\.  
For more information, see [Enhanced support for Java development](enhanced-java.md)\.


## C++ sample

- **Note**  
To save time, this step builds only the Amazon S3 portion of the AWS SDK for C\+\+\. If you want to build the complete SDK, omit the `-DBUILD_ONLY=s3` from the `cmake` command\.  
Building the complete SDK for C\+\+ can take more than an hour to complete, depending on the computing resources available to your Amazon EC2 instance or your own server\.


## PHP sample

- **Note**  
The following procedure installs PHP only\. To install related tools such as an Apache web server and a MySQL database, see [Tutorial: Installing a LAMP Web Server on Amazon Linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/install-LAMP.html) in the *Amazon EC2 User Guide for Linux Instances*\.
- **Note**  
You can view your version of Amazon Linux using the following command:
- **Note**  
The preceding code doesn't rely on any external files\. However, if you ever include or require other PHP files in your file, and you want AWS Cloud9 to use those files to do code completion as you type, turn on the **Project, PHP Support, Enable PHP code completion** setting in **Preferences**, and then add the paths to those files to the **Project, PHP Support, PHP Completion Include Paths** setting\. \(To view and change your preferences, choose **AWS Cloud9, Preferences** on the menu bar\.\)
- **Note**  
After installation, Composer might suggest that you install additional dependencies\. You can do this with a command such as the following, specifying the list of dependencies to install\. For example, the following command instructs Composer to install the following list of dependencies\.


## Ruby

- **Note**  
Following this tutorial might result in charges to your AWS account\. These include possible charges for services such as Amazon EC2 and Amazon S3\. For more information, see [Amazon EC2 Pricing](https://aws.amazon.com/ec2/pricing/) and [Amazon S3 Pricing](https://aws.amazon.com/s3/pricing/)\.


## TypeScript sample

- **Note**  
Instead of creating a new run configuration in the IDE, you can also execute this code by running the command ** `node hello.js 5 9` ** from the terminal\.


## Docker sample

- **Note**  
If the container stops running, you can no longer use the IDE to access the container until you start running the container again\. To do this, go back to [Step 3: Run the container](#sample-docker-run)\.

