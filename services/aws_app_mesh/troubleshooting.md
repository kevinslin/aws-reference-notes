---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-app-mesh-user-guide.git)
{% endhint %}

## Best practices

- **Note**  
The administration endpoint should never be exposed to the public internet\. Additionally, we recommend monitoring the administration endpoint logs, which are set by the `ENVOY_ADMIN_ACCESS_LOG_FILE` environment variable to `/tmp/envoy_admin_access.log` by default\.
- **Note**  
We do not recommend using the `debug` level in production environments\. Setting the level to `debug` increases the logging and may affect performance and the overall cost of logs offloaded to solutions like [CloudWatch Logs](https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html)\.


## Setup

- **Important**  
Fargate must use a port value greater than 1024\.


## Connectivity

- **Important**  
While the standard SMTP ports are `25`, `587`, and `465`, you should only add the port you are using to `APPMESH_EGRESS_IGNORED_PORTS` and not all three\.
- **Note**  
Setting the mesh outbound filter value affects all virtual nodes within the mesh\.

