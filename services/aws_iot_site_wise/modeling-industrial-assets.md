---
id: Modeling industrial assets
title: Modeling industrial assets
created: 1683841041000
updated: 1683841041000
---
# Modeling industrial assets

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-sitewise-user-guide.git)
{% endhint %}

## Creating asset models

- **Note**  
We recommend that you model your operation starting with the lowest\-level nodes\. For example, create your wind turbine model before you create your wind farm model\. Asset hierarchy definitions contain references to existing asset models\. With this approach, you can define asset hierarchies as you create your models\.
- **Note**  
This example model resembles the wind turbine model from the AWS IoT SiteWise demo\. For more information, see [Using the AWS IoT SiteWise demo](getting-started-demo.md)\.
- **Note**  
This example model resembles the wind farm model from the AWS IoT SiteWise demo\. For more information, see [Using the AWS IoT SiteWise demo](getting-started-demo.md)\.


## Creating assets

- **Note**  
You can only create assets from `ACTIVE` models\. If your model's state isn't `ACTIVE`, you may need to wait for up to a few minutes before you can create assets from that model\. For more information, see [Asset and model states](asset-and-model-states.md)\.


## Mapping industrial data streams to asset properties

- **Note**  
This section describes how to set property aliases for measurement properties\. For more information about how to set property aliases for external alarm state properties, see [Mapping external alarm state streams](connect-alarm-data-streams.md)\.


## Updating assets and models

- **Important**  
If you remove a property from an asset model, AWS IoT SiteWise deletes all previous data for that property\. If you remove a hierarchy definition from an asset model, AWS IoT SiteWise disassociates all assets in that hierarchy\.


## Deleting assets and models

- **Important**  
AWS IoT SiteWise deletes all property data for deleted assets\.

