---
id: Interacting with other services
title: Interacting with other services
created: 1683841041000
updated: 1683841041000
---
# Interacting with other services

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-sitewise-user-guide.git)
{% endhint %}

## Working with asset property notifications

- **Important**  
This rule query statement ignores value updates other than the first in each batch\. Each batch can contain up to 10 values\. If you need to include the remaining values, you must set up a more complex solution to output asset property values to other services\. For example, you can set up a rule with an AWS Lambda action to republish each value in the array to another topic, and set up another rule to query that topic and publish each value to the desired rule action\.

