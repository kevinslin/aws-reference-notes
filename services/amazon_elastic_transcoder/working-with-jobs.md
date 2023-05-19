---
id: Working with Jobs
title: Working with Jobs
created: 1683841041000
updated: 1683841041000
---
# Working with Jobs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-transcoder-developer-guide.git)
{% endhint %}

## Creating a Job

- **Note**  
Before you can create a job, you must create the pipeline \(the queue\) that will manage the job\. For more information about creating a pipeline, see [Creating a Pipeline in Elastic Transcoder](creating-pipelines.md)\. In addition, if you want to transcode a file using settings other than those provided in the Elastic Transcoder default presets, you must create a new preset\. For more information about creating a preset, see [Creating a Preset in Elastic Transcoder](creating-presets.md)\.


## Listing and Viewing Jobs

- **Note**  
When you list jobs by pipeline, Elastic Transcoder lists all of the jobs that you've created in the last six months for that pipeline\. When you list jobs by status, Elastic Transcoder lists all of the jobs that you created during the past six months that currently have the specified status\.
- **Note**  
If you have specified more than one output for your jobs \(for example, one output for the Kindle Fire and another output for the Apple iPhone 4s\), you currently must use the Elastic Transcoder API to list the jobs\.


## Job Settings

- **Note**  
You can configure Elastic Transcoder to notify you when the status of a job changes, including when Elastic Transcoder starts and finishes processing a job, and when Elastic Transcoder encounters a warning or error condition\. For more information, see [Notifications of Job Status](notifications.md)\.
- **Note**  
Album art is available for audio\-only outputs in `flac`, `mp3`, or `mp4` containers\.
- **Note**  
HLS content protection encrypts each individual segment of a file, and Elastic Transcoder does not support HLS content protection combined with file\-level encryption\.
- **Note**  
PlayReady DRM, HLS content protection, and output encryption are mutually exclusive options\.

