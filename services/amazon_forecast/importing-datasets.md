---
id: Importing Datasets
title: Importing Datasets
created: 1683841041000
updated: 1683841041000
---
# Importing Datasets

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-forecast-developer-guide.git)
{% endhint %}

## Related Time Series

- **Note**  
 A related time series that contains any values within the forecast horizon is treated as a forward\-looking time series\.
- **Note**  
To upgrade an existing predictor to AutoPredictor, see [Upgrading to AutoPredictor](howitworks-predictor.md#upgrading-autopredictor)


## Item Metadata

- **Note**  
To upgrade an existing predictor to AutoPredictor, see [Upgrading to AutoPredictor](howitworks-predictor.md#upgrading-autopredictor)


## Handling Missing Values

- **Important**  
For both target and related time series datasets, `mean`, `median`, `min`, and `max` are calculated based on a rolling window of the 64 most recent data entries before the missing values\.

