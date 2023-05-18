---
id: Working with objects
title: Working with objects
created: 1683841041000
updated: 1683841041000
---
# Working with objects

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-s3-userguide.git)
{% endhint %}

## Creating object keys

- **Note**  
Object key names with the value "soap" aren't supported for [virtual\-hosted\-style requests](https://docs.aws.amazon.com/AmazonS3/latest/userguide/VirtualHosting.html#virtual-hosted-style-access)\. For object key name values where "soap" is used, a [path\-style URL](https://docs.aws.amazon.com/AmazonS3/latest/userguide/VirtualHosting.html#path-style-access) must be used instead\.
- **Note**  
Objects with key names ending with period\(s\) "\." downloaded using the Amazon S3 console will have the period\(s\) "\." removed from the key name of the downloaded object\. To download an object with the key name ending in period\(s\) "\." retained in the downloaded object, you must use the AWS Command Line Interface \(AWS CLI\), AWS SDKs, or REST API\.  
In addition, be aware of the following prefix limitations:  
Objects with a prefix of "\./" must be uploaded or downloaded with the AWS Command Line Interface \(AWS CLI\), AWS SDKs, or REST API\. You cannot use the Amazon S3 console\.
Objects with a prefix of "\.\./" cannot be uploaded using the AWS Command Line Interface \(AWS CLI\) or Amazon S3 console\.


## Working with metadata

- **Note**  
The `PUT` request header is limited to 8 KB in size\. Within the `PUT` request header, the system\-defined metadata is limited to 2 KB in size\. The size of system\-defined metadata is measured by taking the sum of the number of bytes in the US\-ASCII encoding of each key and value\.
- **Note**  
 SOAP support over HTTP is deprecated, but SOAP is still available over HTTPS\. New Amazon S3 features are not supported for SOAP\. Instead of using SOAP, we recommend that you use either the REST API or the AWS SDKs\.
- **Note**  
The `PUT` request header is limited to 8 KB in size\. Within the `PUT` request header, the user\-defined metadata is limited to 2 KB in size\. The size of user\-defined metadata is measured by taking the sum of the number of bytes in the UTF\-8 encoding of each key and value\.


## Uploading objects

- **Note**  
If you rename an object or change any of the properties in the Amazon S3 console, for example **Storage Class**, ** Encryption**, or **Metadata**, a new object is created to replace the old one\. If S3 Versioning is enabled, a new version of the object is created, and the existing object becomes an older version\. The role that changes the property also becomes the owner of the new object \(or object version\)\.


## Using multipart upload

- **Note**  
After you initiate a multipart upload and upload one or more parts, you must either complete or stop the multipart upload to stop getting charged for storage of the uploaded parts\. Only *after* you either complete or stop a multipart upload will Amazon S3 free up the parts storage and stop charging you for the parts storage\.  
After stopping a multipart upload, you cannot upload any part using that upload ID again\. If any part uploads were in\-progress, they can still succeed or fail even after you stop the upload\. To make sure you free all storage consumed by all parts, you must stop a multipart upload only after all part uploads have been completed\.
- **Important**  
If you are using a multipart upload with additional checksums, the multipart part numbers must use consecutive part numbers\. When using additional checksums, if you try to complete a multipart upload request with nonconsecutive part numbers, Amazon S3 generates HTTP `500 Internal Server Error` error\.
- **Note**  
It is possible for some other request received between the time you initiated a multipart upload and completed it to take precedence\. For example, if another operation deletes a key after you initiate a multipart upload with that key, but before you complete it, the complete multipart upload response might indicate a successful object creation without you ever seeing the object\.
- **Note**  
To minimize your storage costs, we recommend that you configure a lifecycle rule to delete incomplete multipart uploads after a specified number of days by using the `AbortIncompleteMultipartUpload` action\. For more information about creating a lifecycle rule to delete incomplete multipart uploads, see [Configuring a bucket lifecycle configuration to delete incomplete multipart uploads](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/mpu-abort-incomplete-mpu-lifecycle-config.html)\.


## Copying objects

- **Note**  
Copying objects across locations incurs bandwidth charges\. 
 If the source object is archived in `S3 Glacier Flexible Retrieval` or `S3 Glacier Deep Archive`, you must first restore a temporary copy before you can copy the object to another bucket\. For information about archiving objects, see [Transitioning to the S3 Glacier Flexible Retrieval and S3 Glacier Deep Archive storage classes \(object archival\)](lifecycle-transition-general-considerations.md#before-deciding-to-archive-objects)\.
- **Note**  
Objects encrypted with customer\-provided encryption keys \(SSE\-C\) cannot be copied or moved using the S3 console\. To copy or move objects encrypted with SSE\-C, use the AWS CLI, AWS SDK, or the Amazon S3 REST API\.
When copying an object by using the Amazon S3 console, you must grant permission `s3:ListAllMyBuckets`\. The console needs this permission to validate the copy operation\.
- **Note**  
This action creates a copy of all specified objects with updated settings, updates the last\-modified date in the specified location, and adds a delete marker to the original object\. 
When moving folders, wait for the move action to finish before making additional changes in the folders\. 
This action updates metadata for bucket versioning, encryption, Object Lock features, and archived objects\.


## Downloading an object

- **Note**  
You can only download one object at a time\.
Objects with key names ending with period\(s\) "\." downloaded using the Amazon S3 console will have the period\(s\) "\." removed from the key name of the downloaded object\. To download an object with the key name ending in period\(s\) "\." retained in the downloaded object, you must use the AWS Command Line Interface \(AWS CLI\), AWS SDKs, or REST API\. For AWS CLI, REST API, and AWS SDK information and examples, see [Downloading an object](https://docs.aws.amazon.com/AmazonS3/latest/userguide/download-objects.html)\.
- **Note**  
Your network connection remains open until you read all of the data or close the input stream\. We recommend that you read the content of the stream as quickly as possible\.


## Checking object integrity

- **Important**  
If you're using a multipart upload with additional checksums, the multipart part numbers must use consecutive part numbers\. When using additional checksums, if you try to complete a multipart upload request with nonconsecutive part numbers, Amazon S3 generates an HTTP `500 Internal Server Error` error\.
- **Important**  
If you're using S3 Object Lambda, all requests to S3 Object Lambda are signed using `s3-object-lambda` instead of `s3`\. This behavior affects the signature of trailing checksum values\. For more information about S3 Object Lambda, see [Transforming objects with S3 Object Lambda](transforming-objects.md)\.
- **Note**  
Objects that are larger than the size limitations of the `CopyObject` API operation must use multipart copy commands\.
- **Important**  
When you perform some operations using the AWS Management Console, Amazon S3 uses a multipart upload if the object is greater than 16 MB in size\. In this case, the checksum is not a direct checksum of the full object, but rather a calculation based on the checksum values of each individual part\.   
For example, consider an object 100 MB in size that you uploaded as a single\-part direct upload using the REST API\. The checksum in this case is a checksum of the entire object\. If you later use the console to rename that object, copy it, change the storage class, or edit the metadata, Amazon S3 uses the multipart upload functionality to update the object\. As a result, Amazon S3 creates a new checksum value for the object that is calculated based on the checksum values of the individual parts\.  
**The preceding list of console operations is not a complete list of all the possible actions that you can take in the AWS Management Console that result in Amazon S3 updating the object using the multipart upload functionality\.** Keep in mind that whenever you use the console to act on objects over 16 MB in size, the checksum value might not be the checksum of the entire object\.


## Using presigned URLs

- **Important**  
For all Regions that launched after March 20, 2019, if a request arrives at the wrong Amazon S3 location, Amazon S3 returns an HTTP 400 Bad Request error\.
- **Note**  
If you created a presigned URL using a temporary token, the URL expires when the token expires, even if the URL was created with a later expiration time\.
Because presigned URLs grant access to your Amazon S3 buckets to whoever has the URL, we recommend that you protect them appropriately\.

