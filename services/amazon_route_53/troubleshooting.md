---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-route53-docs.git)
{% endhint %}

## My domain is unavailable on the internet

- **Important**  
If you specified the wrong name server records when you transferred the domain to Route 53, it can take up to two days after you correct the name servers for the domain before DNS service is fully restored\. This is because DNS resolvers across the internet typically request the name servers only once every two days and cache the answer\.<a name="troubleshooting-domain-unavailable-transferred-domain-wrong-name-servers-procedure-1"></a>
- **Important**  
Restoring internet service for the domain can take up to 48 hours\.<a name="troubleshooting-domain-unavailable-deleted-hosted-zone-procedure"></a>


## My domain is suspended (status is ClientHold)

- **Note**  
If you need help getting your domain unsuspended, you can contact AWS Support free of charge\. For more information, see [Contacting AWS Support about domain registration issues](domain-contact-support.md)\.
- **Note**  
If you don't respond to the first email, we resend the email up to two more times\. If you have already registered one or more domains with Amazon Route 53 and used the same email address for the registrant contact, we don't send a confirmation email\.


## I changed DNS settings, but they haven't taken effect

- **Note**  
If you aren't sure you did this part, see [You recently transferred DNS service to Amazon Route 53, but you didn't update the name servers with the domain registrar](#troubleshooting-new-dns-settings-not-in-effect-recent-transfer-wrong-name-servers)\.
- **Important**  
When you change the name servers for the domain to the name servers from your Route 53 hosted zone, it can take up to two days for the change to take effect and for Route 53 to become your DNS service\. This is because DNS resolvers across the internet typically request the name servers only once every two days and cache the answer\.
- **Note**  
For alias records, the TTL is determined by the AWS resource that the record routes traffic to\. For more information, see [Choosing between alias and non\-alias records](resource-record-sets-choosing-alias-non-alias.md)\.<a name="troubleshooting-new-dns-settings-not-in-effect-cached-resource-record-set-procedure"></a>


## My AWS account is closed, suspended, or terminated, and my domain is registered with Route 53

- **Note**  
Once 90 days has passed from when you closed your account, you can no longer reopen it\. For more information, see [Can I reopen my closed AWS account?](https://aws.amazon.com/premiumsupport/knowledge-center/reopen-aws-account/)\.

