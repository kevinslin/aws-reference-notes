---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-step-functions-developer-guide.git)
{% endhint %}

## General troubleshooting

- **Tip**  
Use the [ data flow simulator in the Step Functions console](https://console.aws.amazon.com/states/home?region=us-east-1#/simulator) to test JSON path syntax, to better understand how data is manipulated within a state, and to see how data is passed between states\.


## Troubleshooting service integrations

- **Note**  
You can try to use `.waitForTaskToken` with any API action\. However, some APIs don't have any suitable parameters\.

