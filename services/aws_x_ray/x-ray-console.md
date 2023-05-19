---
id: X-Ray console
title: X-Ray console
created: 1683841041000
updated: 1683841041000
---
# X-Ray console

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-xray-developer-guide.git)
{% endhint %}

## Service map

- **Note**  
The X\-Ray service map can display up to 10,000 nodes\. In rare scenarios where the total number of service nodes exceeds this limit, you may receive an error and be unable to display a complete service map in the console\.


## Filter expressions

- **Note**  
If you choose a relative time range in the service map and choose a node, the console converts the time range to an absolute start and end time\. To ensure that the traces for the node appear in the search results, and avoid scanning times when the node wasn't active, the time range only includes times when the node sent traces\. To search relative to the current time, you can switch back to a relative time range in the traces page and scan again\.
- **Note**  
If the service encounters an error in qualifying a group, that group is no longer included in processing incoming traces and an error metric is recorded\.


## Tracing event-driven applications

- **Note**  
Each trace segment can be linked to up to 20 traces, while a trace can include a maximum of 100 links\. In certain scenarios, linking additional traces may result in exceeding the [maximum trace document size](https://docs.aws.amazon.com/general/latest/gr/xray.html#limits_xray), causing a potentially incomplete trace\. This can happen, for example, when a Lambda function with tracing enabled sends many SQS messages to a queue in a single invocation\. If you encounter this issue, a mitigation is available which uses the X\-Ray SDKs\. See the X\-Ray SDK for [Java](https://github.com/aws/aws-xray-sdk-java#oversampling-mitigation), [Node\.js](https://github.com/aws/aws-xray-sdk-node/tree/master/packages/core#oversampling-mitigation), [Python](https://github.com/aws/aws-xray-sdk-python#oversampling-mitigation), [Go](https://github.com/aws/aws-xray-sdk-go#oversampling-mitigation), or [\.NET](https://github.com/aws/aws-xray-sdk-dotnet#oversampling-mitigation) for more information\.


## Insights

- **Note**  
X\-Ray uses GetInsightSummaries, GetInsight, GetInsightEvents, and GetInsightImpactGraph API operations to retrieve data from insights\. To view insights, use the AWSXrayReadOnlyAccess IAM managed policy or add the following custom policy to your IAM role:
- **Note**  
 X\-Ray insights notifications sends events to Amazon EventBridge, which does not currently support customer managed keys\. For more information, see [Data protection in AWS X\-Ray](xray-console-encryption.md)\.


## Groups

- **Note**  
Groups are billed by the number of retrieved traces that match the filter expression\. For more information, see [AWS X\-Ray pricing](https://aws.amazon.com/xray/pricing/)\.
- **Note**  
You can now configure X\-Ray groups from within the Amazon CloudWatch console\. You can also continue to use the X\-Ray console\.


## Sampling

- **Note**  
X\-Ray uses a best\-effort approach in applying sampling rules, and in some cases the effective sampling rate may not exactly match the configured sampling rules\. However, over time the number of requests sampled should be close to the configured percentage\.

