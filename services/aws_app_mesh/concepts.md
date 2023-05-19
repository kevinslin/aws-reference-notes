---
id: Concepts
title: Concepts
created: 1683841041000
updated: 1683841041000
---
# Concepts

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-app-mesh-user-guide.git)
{% endhint %}

## Meshes

- **Note**  
When creating a Mesh, you must add a namespace selector\. If the namespace selector is empty, it selects all namespaces\. To restrict the namespaces, use a label to associate App Mesh resources to the created mesh\.


## Virtual services

- **Note**  
You can't delete a virtual service that is referenced by a gateway route\. You need to delete the gateway route first\.


## Virtual gateways

- **Important**  
A virtual gateway with a HTTP or HTTP2 listener rewrites the incoming request's hostname to the Gateway Route target Virtual Service's name, and the matched prefix from the Gateway Route is rewritten to `/`, by default\. For example, if you have configured the Gateway route match prefix to `/chapter`, and, if the incoming request is `/chapter/1`, the request would be rewritten to `/1`\. To configure rewrites, refer to the [Creating a gateway route](https://docs.aws.amazon.com/app-mesh/latest/userguide/gateway-routes.html#create-gateway-route) section from Gateway Routes\.  
When creating a virtual gateway, `proxyConfiguration` and `user` should not be configured\.
- **Note**  
When creating a Virtual Gateway, you must add a namespace selector with a label to identify the list of namespaces with which to associate Gateway Routes to the created Virtual Gateway\.


## Virtual nodes

- **Note**  
By default, App Mesh uses the name of the resource you specified in `APPMESH_RESOURCE_ARN` when Envoy is referring to itself in metrics and traces\. You can override this behavior by setting the `APPMESH_RESOURCE_CLUSTER` environment variable with your own name\.
- **Note**  
The connectionPool and portMapping protocols must be the same\. If your listener protocol is tcp, specify maxConnections only\. If your listener protocol is grpc or http2, specify maxRequests only\. If your listener protocol is http, you can specify both maxConnections and maxPendingRequests\. 
      + For **Maximum connections**, specify the maximum number of outbound connections\.
      + \(Optional\) For **Maximum pending requests**, specify the number of overflowing requests after **Maximum connections** that an Envoy will queue\. The default value is `2147483647`\.
- **Note**  
To effectively configure outlier detection for a server Virtual Node, the service discovery method of that Virtual Node should use AWS Cloud Map\. Otherwise if using DNS, the Envoy proxy would only elect a single IP address for routing to the upstream service, nullifying the outlier detection behavior of ejecting an unhealthy host from a set of hosts\. Refer to the Service discovery method section for more details on the Envoy proxy's behavior in relation to the service discovery type\. 
      + For **Server errors**, specify the number of consecutive 5xx errors required for ejection\.
      + For **Outlier detection interval**, specify the time interval and unit between ejection sweep analysis\.
      + For **Base ejection duration**, specify the base amount of time and unit for which a host is ejected\.
      + For **Ejection percentage**, specify the maximum percentage of hosts in the load balancing pool that can be ejected\.
- **Note**  
You can't delete a virtual node if it is specified as a target in any [route](routes.md) or as a provider in any [virtual service](virtual_services.md)\.


## Virtual routers

- **Note**  
You cannot delete a virtual router if it has any [routes](routes.md) or if it is specified as a provider for any [virtual service](virtual_services.md)\.

