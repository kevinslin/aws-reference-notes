---
id: How it works
title: How it works
created: 1683841041000
updated: 1683841041000
---
# How it works

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-deepracer-developer-guide.git)
{% endhint %}

## Reinforcement learning

- **Note**  
 Strictly speaking, the environment state refers to everything relevant to the problem\. For example, the vehicle's position on the track as well as the shape of the track\. The image fed through the camera mounted the vehicle's front does not capture the entire environment state\. Hence, the environment is deemed partially observed and the input to the agent is referred to as *observation *rather than state\. For simplicity, we use *state* and *observation* interchangeably throughout this documentation\.

