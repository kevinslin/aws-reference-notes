---
id: Getting started
title: Getting started
created: 1683841041000
updated: 1683841041000
---
# Getting started

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-app-mesh-user-guide.git)
{% endhint %}

## App Mesh and Amazon ECS

- **Important**  
Only version v1\.9\.0\.0\-prod or later is supported for use with App Mesh\.
- **Important**  
Only version v1\.9\.0\.0\-prod or later is supported for use with App Mesh\.
- **Note**  
The Envoy container definition must be marked as `essential`\.
We recommend allocating `512` CPU units and at least `64` MiB of memory to the Envoy container\. On Fargate the lowest you will be able to set is `1024` MiB of memory\.
The virtual node name for the Amazon ECS service must be set to the value of the `APPMESH_RESOURCE_ARN` property\. This property requires version `1.15.0` or later of the Envoy image\. For more information, see [Envoy image](envoy.md)\.
The value for the `user` setting must match the `IgnoredUID` value from the task definition proxy configuration\. In this example, we use `1337`\. 
The health check shown here waits for the Envoy container to bootstrap properly before reporting to Amazon ECS that the Envoy container is healthy and ready for the application containers to start\. 
By default, App Mesh uses the name of the resource you specified in `APPMESH_RESOURCE_ARN` when Envoy is referring to itself in metrics and traces\. You can override this behavior by setting the `APPMESH_RESOURCE_CLUSTER` environment variable with your own name\. This property requires version `1.15.0` or later of the Envoy image\. For more information, see [Envoy image](envoy.md)\.
- **Important**  
Fargate must use a port value greater than 1024\.
- **Note**  
For more examples and walkthroughs for App Mesh, see the [App Mesh examples repository](https://github.com/aws/aws-app-mesh-examples)\.


## App Mesh and Kubernetes

- **Note**  
The App Mesh controller is not available for Amazon EKS private clusters\.
- **Note**  
If your Amazon EKS cluster family is `IPv6`, please set the cluster name when deploying the App Mesh controller by adding the following option to the previous command `--set clusterName=$CLUSTER_NAME`\.
**Important**  
If your cluster is in the `me-south-1`, `ap-east-1`, `ap-southeast-3`, `eu-south-1`, or `af-south-1` Regions, then you need to add the following option to the previous command:  
Replace *account\-id* and *Region\-code* with one of the appropriate sets of values\.
- **Note**  
If you view the log for the running container, you may see a line that includes the following text, which can be safely ignored\.
- **Important**  
Once the controller has created an App Mesh resource, we recommend that you only make changes to or delete the App Mesh resource using the controller\. If you make changes to or delete the resource using App Mesh, the controller won't change or recreate the changed or deleted App Mesh resource for ten hours, by default\. You can configure this duration to be less\. For more information, see [Configuration](https://github.com/aws/eks-charts/blob/master/stable/appmesh-controller/README.md#configuration) on GitHub\.
- **Important**  
The value for the `app` `matchLabels` `selector` in the spec must match the value that you specified when you created the virtual node in sub\-step `3` of [Step 2: Deploy App Mesh resources](#configure-app-mesh), or the sidecar containers won't be injected into the pod\. In the previous example, the value for the label is `my-app-1`\. If you deploy a virtual gateway, rather than a virtual node, then the `Deployment` manifest should include only the Envoy container\. For more information about the image to use, see [Envoy image](envoy.md)\. For a sample manfest, see the [deployment example](https://github.com/aws/aws-app-mesh-examples/blob/main/walkthroughs/howto-k8s-ingress-gateway/v1beta2/manifest.yaml.template#L585) on GitHub\.
- **Note**  
For more examples and walkthroughs for App Mesh, see the [App Mesh examples repository](https://github.com/aws/aws-app-mesh-examples)\.


## App Mesh and Amazon EC2

- **Note**  
The `APPMESH_RESOURCE_ARN` property requires version `1.15.0` or later of the Envoy image\. For more information, see [Envoy image](envoy.md)\.
**Important**  
Only version v1\.9\.0\.0\-prod or later is supported for use with App Mesh\.
- **Note**  
For more examples and walkthroughs for App Mesh, see the [App Mesh examples repository](https://github.com/aws/aws-app-mesh-examples)\.

