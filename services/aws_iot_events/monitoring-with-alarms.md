---
id: Monitoring with alarms
title: Monitoring with alarms
created: 1683841041000
updated: 1683841041000
---
# Monitoring with alarms

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-iot-events-developer-guide.git)
{% endhint %}

## Managing alarm notifications

- **Note**  
AWS Lambda retries function errors twice\. If the function doesn't have enough capacity to handle all incoming requests, events might wait in the queue for hours or days to be sent to the function\. You can configure an undelivered\-message queue \(DLQ\) on the function to capture events that weren't successfully processed\. For more information, see [Asynchronous invocation](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html) in the *AWS Lambda Developer Guide*\.

