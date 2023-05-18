---
id: Security in EC2 Image Builder
title: Security in EC2 Image Builder
created: 1683841041000
updated: 1683841041000
---
# Security in EC2 Image Builder

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/ec2-image-builder-user-guide.git)
{% endhint %}

## Best practices

- **Note**  
We recommend that you configure all EC2 instances that Image Builder launches from a pipeline build to use IMDSv2 so that instance metadata retrieval requests require a signed token header\.
- **Important**  
If you override **User data** in your recipe, the script doesn't run\. In that case, make sure that you include a command in your user data that creates an empty file named `perform_cleanup`\. Image Builder detects this file and runs the clean\-up script prior to creating the new image\.
- **Important**  
Skipping sections in the clean up script can result in sensitive information, such as owner account details or SSH keys being included in the final image, and in any instance launched from that image\. You might also experience problems with launching in different Availability Zones, Regions, or accounts\.
- **Note**  
The files that you create to skip a section of the clean up script should not include a file extension\. For example, if you want to skip the `CLOUD_INIT_FILES` section of the script, but you create a file named `skip_cleanup_cloudinit_files.txt`, Image Builder will not recognize the skip file\.

