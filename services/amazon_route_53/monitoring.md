---
id: Monitoring
title: Monitoring
created: 1683841041000
updated: 1683841041000
---
# Monitoring

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-route53-docs.git)
{% endhint %}

## Public DNS query logging

- **Note**  
Query logging is also available for private hosted zones\. For more information, see [Resolver query logging](resolver-query-logs.md)\.
- **Note**  
If users are submitting DNS queries for your domain, you should start to see queries in the logs within several minutes after you create the query logging configuration\. <a name="query-logs-configuring-procedure"></a>
- **Note**  
When you configure Route 53 to log DNS queries, you don't incur any Route 53 charges\.


## Resolver query logging

- **Note**  
As is standard for DNS resolvers, resolvers cache DNS queries for a length of time determined by the time\-to\-live \(TTL\) for the resolver\. The Route 53 Resolver caches queries that originate in your VPCs, and responds from the cache whenever possible to speed up responses\. Resolver query logging logs only unique queries, not queries that Resolver is able to respond to from the cache\.  
For example, suppose that an EC2 instance in one of the VPCs that a query logging configuration is logging queries for, submits a request for accounting\.example\.com\. Resolver caches the response to that query, and logs the query\. If the same instance’s elastic network interface makes a query for accounting\.example\.com within the TTL of the Resolver’s cache, Resolver responds to the query from the cache\. The second query is not logged\.

