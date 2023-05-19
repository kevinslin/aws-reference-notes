---
id: Securing Applications
title: Securing Applications
created: 1683841041000
updated: 1683841041000
---
# Securing Applications

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-app-mesh-user-guide.git)
{% endhint %}

## Transport Layer Security (TLS)

- **Note**  
SPIRE is not supported on Amazon ECS\.
- **Note**  
You won't be able to use SPIRE to distribute your certificates if you're using Amazon Elastic Kubernetes Service \(Amazon EKS\) in Fargate mode\.


## Mutual TLS Authentication

- **Note**  
Using App Mesh, you can configure mutual TLS authentication for communications between Envoy proxies from your services\. However, communications between your applications and Envoy proxies are unencrypted\.
- **Important**  
App Mesh doesn't store the certificates or private keys that are used for mutual TLS authentication\. Instead, Envoy stores them in memory\.

