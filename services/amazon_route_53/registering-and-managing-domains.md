---
id: Registering and managing domains
title: Registering and managing domains
created: 1683841041000
updated: 1683841041000
---
# Registering and managing domains

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-route53-docs.git)
{% endhint %}

## Renewing registration for a domain

- **Note**  
You can't use AWS credits to pay the fee for renewing registration for a domain\.
- **Important**  
If you turn off automatic renewal, be aware of the following effects on your domain:  
Some TLD registries delete domains even before the expiration date if you don't renew early enough\. We strongly recommend that you leave automatic renewal enabled if you want to keep a domain name\.
We also strongly recommend that you don't plan to re\-register a domain after it has expired\. Some registrars allow others to register domains immediately after the domains expire, so you might not be able to re\-register before the domain is taken by someone else\.
Some registries charge a large premium to restore expired domains\.
On or near the expiration date, the domain becomes unavailable on the internet\.


## Restoring an expired or deleted domain

- **Important**  
The price for restoring a domain is typically higher and sometimes much higher than the price for registering or renewing a domain\. For the current price for restoring a domain, see the Restoration Price column in [Amazon Route 53 Pricing for Domain Registration](https://d32ze2gidvkk54.cloudfront.net/Amazon_Route_53_Domain_Registration_Pricing_20140731.pdf)\.


## Configuring DNSSEC for a domain

- **Important**  
Amazon Route 53 supports DNSSEC signing and DNSSEC for domain registration\. If you want to configure DNSSEC signing for a domain that's registered with Route 53, see [Configuring DNSSEC signing in Amazon Route 53](dns-configuring-dnssec.md)\.
- **Note**  
We're updating the domains console for Route 53\. During the transition period, you can continue to use the old console\.
- **Important**  
If DNSSEC is enabled for the domain and you disable DNSSEC with the DNS service, DNS resolvers that support DNSSEC will return a `SERVFAIL` error to clients, and the clients won't be able to access the endpoints that are associated with the domain\.
- **Note**  
We're updating the domains console for Route 53\. During the transition period, you can continue to use the old console\.


## Finding your registrar

- **Note**  
This command only runs in us\-east\-1 AWS Region\.


## Deleting a domain name registration

- **Note**  
We're updating the domains console for Route 53\. During the transition period, you can continue to use the old console\.


## Downloading a domain billing report

- **Note**  
If you use invoiced payments, any Route 53 domain registration transactions appear in your monthly AWS invoice\. The invoice includes the domain name and operation that each charge applies to\.

