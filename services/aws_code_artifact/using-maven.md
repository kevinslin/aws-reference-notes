---
id: Using Maven
title: Using Maven
created: 1683841041000
updated: 1683841041000
---
# Using Maven

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-codeartifact-user-guide.git)
{% endhint %}

## Use CodeArtifact with mvn

- **Important**  
You can use any value in the `<id>` element, but it must be the same in both the `<server>` and `<repository>` elements\. This enables the specified credentials to be included in requests to CodeArtifact\.
- **Note**  
The example above publishes `commons-cli 1.4`\. Modify the groupId, artifactID, version, and file arguments to publish a different JAR\.


## Publishing with curl

- **Important**  
You must prefix the value of the `--data-binary` parameter with a `@` character\. When putting the value in quotation marks, the `@` must be included inside the quotation marks\.


## Use Maven checksums

- **Note**  
 Maven uses the term `artifact`\. In this guide, a Maven package is the same as a Maven artifact\. For more information, see [AWS CodeArtifact package](https://docs.aws.amazon.com/codeartifact/latest/ug/welcome.html#welcome-concepts-package)\.

