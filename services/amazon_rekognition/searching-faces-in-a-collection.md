---
id: Searching faces in a collection
title: Searching faces in a collection
created: 1683841041000
updated: 1683841041000
---
# Searching faces in a collection

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/amazon-rekognition-developer-guide.git)
{% endhint %}

## Tagging collections

- **Note**  
If you do not know the collection's Amazon Resource Name, you can use the `DescribeCollection` operation\.


## Adding faces to a collection

- **Note**  
`DetectFaces` returns the same information, so you don't need to call both `DetectFaces` and `IndexFaces` for the same image\.
- **Note**  
To use quality filtering, you need a collection that's associated with version 3, or higher, of the face model\. To get the version of the face model associated with a collection, call [DescribeCollection](https://docs.aws.amazon.com/rekognition/latest/APIReference/API_DescribeCollection.html)\.


## Searching for a face (image)

- **Note**  
If the service detects multiple faces in the input image, it uses the largest face that's detected for searching the face collection\.

