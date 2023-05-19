---
id: LAGs
title: LAGs
created: 1683841041000
updated: 1683841041000
---
# LAGs

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-direct-connect-user-guide.git)
{% endhint %}

## Create a LAG

- **Important**  
For existing connections, connectivity to AWS is interrupted during the creation of the LAG\.


## Update a LAG

- **Note**  
If you adjust the threshold value for the minimum number of operational connections, ensure that the new value does not cause the LAG to fall below the threshold and become non\-operational\.


## Associate a connection with a LAG

- **Important**  
Connectivity to AWS over the connection is interrupted during association\.


## Disassociate a connection from a LAG

- **Important**  
Your connection to AWS is broken off during disassociation\.


## Associate a MACsec CKN/CAK with a LAG

- **Note**  
You cannot modify a MACsec secret key after you associate it with a LAG\. If you need to modify the key, disassociate the key from the connection, and then associate a new key with the connection\. For information about removing an association, see [Remove the association between a MACsec secret key and a LAG](disassociate-key-lag.md)\.

