---
id: Best Practices
title: Best Practices
created: 1683841041000
updated: 1683841041000
---
# Best Practices

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-snowball-developer-guide.git)
{% endhint %}

## Performance

- **Note**  
If you are using a Snowball Edge with the S3 data transfer mechanism, the data transfer rate using the file interface is typically between 25 MB/s and 40 MB/s\. If you need to transfer data faster than this, use the Amazon S3 adapter\. The S3 interface has a data transfer rate typically between 250 MB/s and 400 MB/s\. For more information about using the Amazon S3 adapter, see [Transferring files using the Amazon S3 adapter for data migration](using-adapter.md)  
If you are using a Snowball Edge with the NFS data transfer mechanism, the data transfer rate using the file interface is typically between 250 MB/s and 400 MB/s\. For more information about using the file interface, see [Transferring Files to Snowball Edge devices using the File Interface](using-fileinterface.md)\.

