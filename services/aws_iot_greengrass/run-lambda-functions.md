---
id: Run Lambda functions
title: Run Lambda functions
created: 1683841041000
updated: 1683841041000
---
# Run Lambda functions

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Import a Lambda function as a component (console)

- **Note**  
You can also specify custom platform attributes when you deploy the Greengrass nucleus component to a core device\. For more information, see the [platform overrides parameter](greengrass-nucleus-component.md#greengrass-nucleus-component-configuration-platform-overrides) of the [Greengrass nucleus component](greengrass-nucleus-component.md)\.
- **Important**  <a name="import-v1-lambda-note"></a>
To import a Lambda function that you created to run on AWS IoT Greengrass V1, you must define individual component dependencies for the features that your function uses, such as secrets, local shadows, and stream manager\. Define these components as [hard dependencies](component-recipe-reference.md) so that your Lambda function component restarts if the dependency changes state\. For more information, see [Import V1 Lambda functions](set-up-v2-test-device.md#run-v1-lambda-functions)\.


## Import a Lambda function (CLI)

- **Important**  
You must specify an ARN that includes the version of the function to import\. You can't use version aliases like `$LATEST`\.

