# AWS Reference Notes

<figure><img src="assets/images/cloud-ref-notes.png" alt="Cloud Reference Notes", height="400px" </figure>

I used to have a running joke with colleagues that any part of the aws documentation that started with a **Note** was simply footgun waiting to blow up. 

These footguns came in the form of technical considerations, exceptions, and caveats that would take anywhere between an hour or a month to work around. 

Some examples:
- when provisioning anything via cloudformation/cdk/terraform, reverse engineering what IAM permissions, security groups, versions, and other settings needed to be in place to have a successful deployment
- service limits 
- cross account restrictions
- limitations when integrating different services
- caveats around emitted metrics

This is a compilation of all **Note-able** areas of the AWS Docs, extracted from the AWS public documentation.

I've started with just three AWS Services to make sure that the formatting and information is correct before expanding the scope to other services. 
