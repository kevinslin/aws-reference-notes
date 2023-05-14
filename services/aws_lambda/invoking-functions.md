---
id: Invoking functions
title: Invoking functions
created: 1683841041000
updated: 1683841041000
---
# Invoking functions
## Synchronous invocation

- **Note**  
For functions with a long timeout, your client might be disconnected during synchronous invocation while it waits for a response\. Configure your HTTP client, SDK, firewall, proxy, or operating system to allow for long connections with timeout or keep\-alive settings\.


## Asynchronous invocation

- **Note**  
To prevent a function from triggering, you can set the function's reserved concurrency to zero\. When you set reserved concurrency to zero for an asynchronously\-invoked function, Lambda begins sending new events to the configured [dead\-letter queue](#invocation-dlq) or the on\-failure [event destination](#invocation-async-destinations), without any retries\. To process events that were sent while reserved concurrency was set to zero, you need to consume the events from the dead\-letter queue or the on\-failure event destination\.


## Event filtering

- **Note**  
Like EventBridge, for strings, Lambda uses exact character\-by\-character matching without case\-folding or any other string normalization\. For numbers, Lambda also uses string representation\. For example, 300, 300\.0, and 3\.0e2 are not considered equal\.
- **Note**  
By default, you can have five different filters per event source\. You can [request a quota increase](https://docs.aws.amazon.com/servicequotas/latest/userguide/request-quota-increase.html) for up to 10 filters per event source\. The Lambda console lets you add up to 10 filters depending on the current quota for your account\. If you attempt to add more filters than your current quota allows, Lambda throws an error when you try to create the event source\.
- **Note**  
After you attach filter criteria to a Kafka or Amazon MQ event source mapping, it can take up to 15 minutes to apply your filtering rules to events\.


## Function URLs

- **Note**  
You can access your function URL through the public Internet only\. While Lambda functions do support AWS PrivateLink, function URLs do not\.

