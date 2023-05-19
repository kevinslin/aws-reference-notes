---
id: Envoy
title: Envoy
created: 1683841041000
updated: 1683841041000
---
# Envoy

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-app-mesh-user-guide.git)
{% endhint %}

## Envoy configuration variables

- **Note**  
App Mesh Envoy 1\.17 doesn't supports Envoy’s **v2 xDS** API\. If you're using [Envoy configuration variables](https://docs.aws.amazon.com/app-mesh/latest/userguide/envoy-config.html) that accept Envoy config files, they must be updated to the latest** v3 xDS** API\.


## Envoy defaults set by App Mesh

- **Note**  
No matter if your Envoys have the Envoy or App Mesh default circuit breaker values, you cannot modify the values\.

