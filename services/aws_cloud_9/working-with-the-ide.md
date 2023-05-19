---
id: Working with the IDE
title: Working with the IDE
created: 1683841041000
updated: 1683841041000
---
# Working with the IDE

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## Tour the IDE

- **Note**  
It can take a few moments for the IDE to display again\.
- **Note**  
This procedure is similar to [Step 2: Basic tour of the IDE](tutorial-tour-ide.md) from either of the [basic IDE tutorials](tutorials-basic.md)\.


## Previewing files

- **Note**  
The **Preview Settings** menu in the file preview tab is currently not functional and choosing any of its menu commands will have no effect\.


## Previewing running applications

- **Note**  
You aren't required to run your application using HTTP over port `8080`, `8081`, or `8082` with the IP address of `127.0.0.1`, `localhost`, or `0.0.0.0`\. However, if you don't do so, you can't preview your running application from within the IDE\.
- **Note**  
The preview application is run within the IDE and is loaded inside an iframe element\. Some application servers might by default block requests that come from iframe elements, such as the X\-Frame\-Options header\. If your preview application isn't displayed in the preview tab, make sure that your application server doesn't prohibit displaying the content in iframes\.
- **Note**  
In the following example, `text/html` is the `Content-Type` of the returned content\. To return the content in a different format, specify a different `Content-Type`\. For example, you can specify `text/css` for a CSS file format\.
- **Note**  
If the application isn't already running, an error appears on the application preview tab\. To resolve this issue, run or restart the application, and then choose the menu bar command again\.  
Suppose that, for example, your application can't run on any of the ports or IPs mentioned\. Or, your application must run on more than one of these ports at the same time\. For example, your application must run on ports `8080` and `3000` at the same time\. If that's the case, then the application preview tab might display an error or might be blank\. This is because the application preview tab within the environment works only with the preceding ports and IPs\. Moreover, the application works with only a single port at a time\.  
We don't recommend sharing the URL in the application preview tab with others\. \(The URL is in the following format: `https://12a34567b8cd9012345ef67abcd890e1.vfs.cloud9.us-east-2.amazonaws.com/`\. In this format, `12a34567b8cd9012345ef67abcd890e1` is the ID that AWS Cloud9 assigns to the environment\. `us-east-2` is the ID for the AWS Region for the environment\.\) This URL works only when the IDE for the environment is open and the application is running in the same web browser\.  
If you attempt to visit the IP of `127.0.0.1`, `localhost`, or `0.0.0.0` by using the application preview tab in the IDE or in a separate web browser tab outside of the IDE, the AWS Cloud9 IDE by default attempts to go to your local computer, instead of the instance or your own server that's connected to the environment\.
- **Note**  
This command doesn't restart the server\. It only refreshes the contents of the application preview tab\.
- **Note**  
The AWS Cloud9 IDE must also be running in at least one other tab in the same web browser\. Otherwise, the application preview isn't displayed in a separate web browser tab\.
- **Note**  
You aren't required run using HTTP over port `8080`, `8081`, or `8082`\. If you don't do this, you can't preview your running application from within the IDE\. For more information, see [Preview a running application](#app-preview-preview-app)\. Otherwise, if you're running on a different protocol or port, substitute it in this step\.  
For an additional layer of security, set up a network access control list \(ACL\) for a subnet in a VPC that the instance can use\. For more information about security groups and network ACLs, see the following:  
 [Step 3: Set up the subnet for the instance](#app-preview-share-subnet) 
 [Security](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html) in the *Amazon VPC User Guide*
 [Security Groups for Your VPC](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) in the *Amazon VPC User Guide*
 [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_ACLs.html) in the *Amazon VPC User Guide*
- **Note**  
You aren't required to run using HTTP over port `8080`, `8081`, or `8082`\. However, if you don't, you can't preview your running application from within the IDE\. For more information, see [Preview a running application](#app-preview-preview-app)\. Otherwise, if you're running on a different protocol or port, substitute it in this step\.  
This step describes how to set up a network ACL for a subnet in an Amazon VPC that the instance can use\. This isn't required but is recommended\. Setting up a network ACL adds an additional layer of security\. For more information about network ACLs, see the following:  
 [Security](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Security.html) in the *Amazon VPC User Guide*
 [Network ACLs](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_ACLs.html) in the *Amazon VPC User Guide*
- **Note**  
Your application's public IP address might change anytime the instance for your application restarts\. To prevent your IP address from changing, allocate an Elastic IP address, and then assign that address to the running instance\. For instructions, see [Allocating an Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#using-instance-addressing-eips-allocating) and [Associating an Elastic IP Address with a Running Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#using-instance-addressing-eips-associating) in the *Amazon EC2 User Guide for Linux Instances*\. Allocating an Elastic IP address might cause your AWS account to incur charges\. For more information, see [Amazon EC2 Pricing](https://aws.amazon.com/ec2/pricing/)\.  
You're not required to run your application using HTTP over port `8080`, `8081`, or `8082`\. However, if you don't, you can't preview your running application from within the IDE\. For more information, see [Preview a running application](#app-preview-preview-app)\.  
Suppose that, for example, requests that originate from a VPN that blocks traffic over the requested protocol or port\. Then, those requests to access your application's URL might fail\. Request must be made from a different network that allows traffic over the requested protocol and port\. For more information, contact your network administrator\.  
We don't recommend sharing the URL in your application preview tab in the IDE with others\. \(This URL is in the following format: `https://12a34567b8cd9012345ef67abcd890e1.vfs.cloud9.us-east-2.amazonaws.com/`\. In this format, `12a34567b8cd9012345ef67abcd890e1` is the ID that AWS Cloud9 assigns to the environment\. `us-east-2` is the ID of the AWS Region for the environment\.\) This URL works only when the IDE for the environment is open and the application is running in the same web browser\.


## Working with Builders, Runners, and Debuggers

- **Note**  
Any changes you make to a built\-in runner apply only to the environment you made those changes in\. To apply your changes to a separate environment, open the other environment, and then follow the preceding steps to open, edit, and save those same changes to that built\-in runner\.
- **Note**  
Any run configuration you create applies only to the environment you created that run configuration in\. To add that run configuration to a separate environment, open the other environment, and then follow the preceding steps to create the same run configuration in that environment\.
- **Note**  
Any builder or runner you create applies only to the environment you created that builder or runner in\. To add that run builder or runner to a separate environment, open the other environment, and then follow the preceding steps to create the same builder or runner in that environment\.


## Working with Custom Environment Variables

- **Note**  
The **ENV** list is the only approach for getting and setting custom environment variables by using code, separate from a shell script\.


## Working with user settings

- **Note**  
To store and retrieve your IDE settings, AWS Cloud9 uses the internal APIs `GetUserSettings` and `UpdateUserSettings`\.


## Working with themes

- **Important**  
AWS Cloud9 no longer supports the feature that allowed users to override IDE themes by updating the `styles.css` file\. Users can continue to view, edit, and save the `styles.css` file using the editor, but no theme overrides are applied when the AWS Cloud9 IDE loads\.   
 If AWS Cloud9 detects that the `styles.css` file has been modified, the following message is displayed in the IDE:  
Support for theme overrides has been discontinued\. The contents of this styles\.css file will no longer be applied on loading the AWS Cloud9 IDE\.  
If you need to use style sheets to define themes for the IDE, please [contact us](https://aws.amazon.com/contact-us/) directly\.


## Managing initialization scripts

- **Important**  
AWS Cloud9 no longer supports the experimental feature that allowed users to customize an initialization script that was automatically run in the IDE\. Users can continue to view, edit, and save the `init.js` file using the editor, but customized initialization scripts are no longer permitted to run and can't modify the IDE's behavior\.  
 If AWS Cloud9 detects that the `init.js` file has been modified, the following message is displayed in the IDE:  
Support for initialization scripts has been discontinued\. The contents of this init\.js file will no longer be executed on loading the AWS Cloud9 IDE\.  
If you need to run a custom initialization script for the IDE, please [contact us](https://aws.amazon.com/contact-us/) directly\.
- **Important**  
You can edit and save the `init.js` file using the editor, but your customized script will not be permitted to run in the IDE\.

