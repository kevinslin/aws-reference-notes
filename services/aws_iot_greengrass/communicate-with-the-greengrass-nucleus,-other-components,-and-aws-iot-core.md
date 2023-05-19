---
id: 'Communicate with the Greengrass nucleus, other components, and AWS IoT Core'
title: 'Communicate with the Greengrass nucleus, other components, and AWS IoT Core'
created: 1683841041000
updated: 1683841041000
---
# Communicate with the Greengrass nucleus, other components, and AWS IoT Core

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-greengrass-v2-developer-guide.git)
{% endhint %}

## Publish/subscribe local messages

- **Note**  
You can't use this publish/subscribe IPC service to publish or subscribe to AWS IoT Core MQTT\. For more information about how to exchange messages with AWS IoT Core MQTT, see [Publish/subscribe AWS IoT Core MQTT messages](ipc-iot-core-mqtt.md)\.


## Publish/subscribe AWS IoT Core MQTT messages

- **Note**  
This MQTT messaging IPC service lets you exchange messages with AWS IoT Core\. For more information about how to exchange messages between components, see [Publish/subscribe local messages](ipc-publish-subscribe.md)\.


## Interact with component lifecycle

- **Important**  
Local deployments don't notify components before updates\.
- **Tip**  
You can follow a tutorial to learn how to develop a component that conditionally defers component updates\. For more information, see [Tutorial: Develop a Greengrass component that defers component updates](defer-component-updates-tutorial.md)\.
- **Tip**  
You can follow a tutorial to learn how to develop a component that conditionally defers component updates\. For more information, see [Tutorial: Develop a Greengrass component that defers component updates](defer-component-updates-tutorial.md)\.
- **Note**  
This operation can't pause containerized processes, such as Docker containers\. To pause and resume a Docker container, you can use the [docker pause](https://docs.docker.com/engine/reference/commandline/pause/) and [docker resume](https://docs.docker.com/engine/reference/commandline/unpause/) commands\.
- **Important**  
To use this operation, you must define an authorization policy that grants permission to use this operation\. For more information, see [Authorization](#ipc-component-lifecycle-authorization)\.
- **Important**  
To use this operation, you must define an authorization policy that grants permission to do so\. For more information, see [Authorization](#ipc-component-lifecycle-authorization)\.


## Interact with component configuration

- **Important**  
Local deployments don't notify components of updates\.


## Retrieve secret values

- **Important**  
This example component prints the value of a secret, so use it only with secrets that store test data\. Don't use this component to print the value of a secret that stores important information\.
- **Note**  <a name="ipc-secret-manager-authorization-policy-resource-wildcard"></a>
We recommend that in a production environment, you reduce the scope of the authorization policy, so that the component retrieves only the secrets that it uses\. You can change the `*` wildcard to a list of secret ARNs when you deploy the component\.


## Interact with local shadows

- **Note**  <a name="note-requirement-enable-shadow-manager-client-devices"></a>
To enable a core device to interact with client device shadows, you must also configure and deploy the MQTT bridge component\. For more information, see [Enable shadow manager to communicate with client devices](work-with-client-device-shadows.md)\.


## Manage local deployments and components

- **Note**  
This feature is available for v2\.6\.0 and later of the [Greengrass nucleus component](greengrass-nucleus-component.md)\.
- **Note**  
While you can restart any component, we recommend that you restart only [generic components](develop-greengrass-components.md#component-types)\.
- **Note**  
While you can stop any component, we recommend that you stop only [generic components](develop-greengrass-components.md#component-types)\.


## Authenticate and authorize client devices

- **Note**  
This feature is available for v2\.6\.0 and later of the [Greengrass nucleus component](greengrass-nucleus-component.md)\.

