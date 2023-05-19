---
id: Troubleshooting
title: Troubleshooting
created: 1683841041000
updated: 1683841041000
---
# Troubleshooting

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloudhsm-user-guide.git)
{% endhint %}

## Client SDK 5 user contains inconsistent values

- **Note**  
To perform these steps you should ideally be logged in as an admin\. If your admin account is not consistent, go through these steps logging in with the admin and repeating the steps until all properties are consistent\. After your admin account is consistent, you can proceed to use that admin to synchronize other users in the cluster\.


## Non-compliant AES key wraps

- **Important**  
This issue only impacts keys wrapped with version 3\.0\.0 of the PKCS \#11 library\. You can wrap keys using earlier versions \(2\.0\.4 and lower\-numbered packages\) or later versions \(3\.0\.1 and higher\-numbered packages\) of the PKCS \#11 library\.

