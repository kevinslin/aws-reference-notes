---
id: Manage pipelines
title: Manage pipelines
created: 1683841041000
updated: 1683841041000
---
# Manage pipelines

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/ec2-image-builder-user-guide.git)
{% endhint %}

## Use cron expressions

- **Note**  
Cron expressions use Universal Coordinated Time \(UTC\)\. For more information about UTC time, and to find the offset for your time zone, see [Time Zone Abbreviations – Worldwide List](https://www.timeanddate.com/time/zones/)\.
- **Tip**  
If you don't want your pipeline job to extend into the next day while it's running, make sure that you factor in time for your build when you specify the start time\.
- **Tip**  
If you don't want your pipeline job to extend into the next day while it's running, make sure that you factor in time for your build when you specify the start time\.


## Use EventBridge rules

- **Note**  
Event buses are specific to a Region\. The rule and the target must be in the same Region\.
- **Note**  
To learn more about settings for rate expression rules that are not covered in this example, see [Rate expressions](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-create-rule-schedule.html#eb-rate-expressions) in the *Amazon EventBridge User Guide*\.

