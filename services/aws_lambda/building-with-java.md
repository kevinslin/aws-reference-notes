---
id: Building with Java
title: Building with Java
created: 1683841041000
updated: 1683841041000
---
# Building with Java

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-lambda-developer-guide.git)
{% endhint %}

## Deploy .zip file archives

- **Note**  
To keep your deployment package size small, package your function's dependencies in layers\. Layers enable you to manage your dependencies independently, can be used by multiple functions, and can be shared with other accounts\. For more information, see [Creating and sharing Lambda layers](configuration-layers.md)\.


## Logging

- **Note**  
 AWS Lambda does not include Log4j2 in its managed runtimes or base container images\. These are therefore not affected by the issues described in CVE\-2021\-44228, CVE\-2021\-45046, and CVE\-2021\-45105\.   
 For cases where a customer function includes an impacted Log4j2 version, we have applied a change to the Lambda Java [managed runtimes](lambda-runtimes.md) and [base container images](java-image.md) that helps to mitigate the issues in CVE\-2021\-44228, CVE\-2021\-45046, and CVE\-2021\-45105\. As a result of this change, customers using Log4J2 may see an additional log entry, similar to "`Transforming org/apache/logging/log4j/core/lookup/JndiLookup (java.net.URLClassLoader@...)`"\. Any log strings that reference the jndi mapper in the Log4J2 output will be replaced with "`Patched JndiLookup::lookup()`"\.   
 Independent of this change, we strongly encourage all customers whose functions include Log4j2 to update to the latest version\. Specifically, customers using the aws\-lambda\-java\-log4j2 library in their functions should update to version 1\.5\.0 \(or later\), and redeploy their functions\. This version updates the underlying Log4j2 utility dependencies to version 2\.17\.0 \(or later\)\. The updated aws\-lambda\-java\-log4j2 binary is available at the [Maven repository](https://repo1.maven.org/maven2/com/amazonaws/aws-lambda-java-log4j2/) and its source code is available in [Github](https://github.com/aws/aws-lambda-java-libs/tree/master/aws-lambda-java-log4j2)\.


## Errors

- **Note**  
To test this code, you need to include [InputLengthException\.java](https://github.com/awsdocs/aws-lambda-developer-guide/tree/main/sample-apps/java-basic/src/main/java/example/InputLengthException.java) in your project src folder\.


## Tracing

- **Important**  
**ADOT is the preferred method for instrumenting your Lambda functions**\. We recommend using ADOT for all new applications\. However, due to the flexibility OpenTelemetry offers, your Lambda function invocations may experience cold start latency increases\. If you're optimizing for low\-latency and also do not require OpenTelemetry's advanced capabilities such as telemetry correlation and dynamically configurable backend destinations, you may want to use the AWS X\-Ray SDK over ADOT\.
- **Note**  
You cannot configure the X\-Ray sampling rate for your functions\.


## Tutorial - Eclipse IDE

- **Note**  
The AWS SDK Eclipse Toolkit provides an Eclipse plugin for you to both create a deployment package and also upload it to create a Lambda function\. If you can use Eclipse IDE as your development environment, this plugin enables you to author Java code, create and upload a deployment package, and create your Lambda function\. For more information, see the [AWS Toolkit for Eclipse Getting Started Guide](https://docs.aws.amazon.com/AWSToolkitEclipse/latest/GettingStartedGuide/)\. For an example of using the toolkit for authoring Lambda functions, see [Using Lambda with the AWS toolkit for Eclipse](https://docs.aws.amazon.com/AWSToolkitEclipse/latest/GettingStartedGuide/lambda.html)\.
- **Note**  
If you are following other tutorial topics in this guide, the specific tutorials might recommend different package name or class name\.

