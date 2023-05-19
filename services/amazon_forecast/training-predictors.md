---
id: Training Predictors
title: Training Predictors
created: 1683841041000
updated: 1683841041000
---
# Training Predictors

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-forecast-developer-guide.git)
{% endhint %}

## Predictor Metrics

- **Note**  
 For Average wQL, wQL, RMSE, MASE, MAPE, and WAPE metrics, a lower value indicates a superior model\.
- **Note**  
Export files can directly return information from the Dataset Import\. This makes the files vulnerable to CSV injection if the imported data contains formulas or commands\. For this reason, exported files can prompt security warnings\. To avoid malicious activity, disable links and macros when reading exported files\.


## Retraining Predictors

- **Note**  
Retraining is only available for predictors created with AutoPredictor \([`CreateAutoPredictor`](API_CreateAutoPredictor.md)\)\. You can upgrade existing legacy predictors to AutoPredictor\. See [Upgrading to AutoPredictor](howitworks-predictor.md#upgrading-autopredictor)\.


## Weather Index

- **Note**  
You can manually select a time zone outside of the *US region*, *Canada region*, *South America region*, *Central America region*, *Asia Pacific region*, *Europe region*, and *Africa & Middle East region*\. However, all geolocation values must still be within one of those regions\.


## Predictor Explainability

- **Note**  
Predictor Explainability is only available for predictors created with AutoPredictor\. You can upgrade existing legacy predictors to AutoPredictor\. See [Upgrading to AutoPredictor](howitworks-predictor.md#upgrading-autopredictor)\.
- **Note**  
You can create a maximum of one Predictor Explainability per predictor
- **Note**  
Export files can directly return information from the Dataset Import\. This makes the files vulnerable to CSV injection if the imported data contains formulas or commands\. For this reason, exported files can prompt security warnings\. To avoid malicious activity, disable links and macros when reading exported files\.

