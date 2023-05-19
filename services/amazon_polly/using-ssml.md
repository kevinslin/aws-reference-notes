---
id: Using SSML
title: Using SSML
created: 1683841041000
updated: 1683841041000
---
# Using SSML

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-polly-developer-guide.git)
{% endhint %}

## Using SSML in the AWS CLI

- **Important**  
Although you don't use quotation marks around input text in the Amazon Polly console, you must use them in use the AWS CLI It's also important that you differentiate between the quotation marks around input text and quotations required for individual tags\.  
For example, you can use standard quotation marks \("\) to enclose the input text, and single quotation marks \('\) for interior tags, or vice versa\. Either option works for Unix, Linux, and macOS\. However, with Windows you must enclose the input text in standard quotations marks and use single quotation marks for the tags\.   
For all operating systems, you can use standard quotation marks \("\) to enclose the input text, and single quotation marks \('\) for interior tags\)\. For example:
- **Note**  
Some languages are more similar than others, and so some language combinations work better than others\.


## Supported SSML Tags

- **Note**  
The normal speaking rate and volume for a voice falls between the `moderate` and `reduced` levels\.
- **Note**  
Amazon Polly increases the speed no more than 5 times the normal rate\. If text is spoken faster than this, it usually doesn't make sense\. If a speech cannot fit within your specified duration even when speeded up to the maximum, the audio will be speeded up but will last longer than the specified duration\.
- **Note**  
 Some languages may have a different selection of supported parts of speech\.
- **Note**  
The exact length and volume of each attribute value is dependent on the specific Amazon Polly voice used\.
- **Note**  
Unlike the manual mode tag, `<amazon:breath/>`, the `<amazon:auto-breaths>` tag requires a closing tag \(`</amazon:auto-breaths>`\)\.
- **Note**  
When you use "`drc`" in the `amazon:effect `syntax, it is case\-sensitive\.
- **Note**  
When using the `drc` and `prosody volume` tags together, use standard XML practices for nesting tags\.

