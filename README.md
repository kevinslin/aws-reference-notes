# AWS Reference Notes

<figure><img src="assets/images/cloud-ref-notes.png" alt="Cloud Reference Notes", height="400px" </figure>

AWS Reference Notes is a compilation of the **Note-able** sections of AWS services[^1].

It is compiled by parsing all sections of [AWS Documentation](https://docs.aws.amazon.com/) and extracting specific admonitions (eg. **Note**, **Important**, **Considerations**) which are then organized and compiled here. 

AWS Reference Notes exists because I observed that any section of the AWS docs that start with a **Note** was something that was worth paying attention to. These sections documented gotchas, limits, and other caveats of a particular service. When not observed, they can take anywhere on the order of hours to weeks to work around. 

## Layout

Each AWS Service is organized via the following categories

```
- {service}
    - Common
    - Topics
```

### Common

Common refers to parts of an AWS service that is shared among all services. 
Examples of `Common` sections:

- Getting Started
- Monitoring
- Security
- Networking
- Configuration
- Troubleshooting
- Resources and Tags
- Working with other services

### Topics
Topics refers to parts of an AWS service that is service specific. This includes service specific components, features, and runtimes. 

Examples of `Topics` sections:
- ECS Clusters
- S3 Clacier Vaults
- KMS Keys

## Acknowledgements

All content in this site (besides this page) is generated from the official AWS Developer Docs, licensed under the [Creative Commons Attribution 4.0 International](https://github.com/open-guides/og-aws/blob/master/LICENSE.txt)

## Contributing

This project is hot off the press as of 2023-05-14. 

All the notes in this project are auto-generated from [aws-doc-extractor](https://github.com/kevinslin/aws-doc-extractor)
See the repo for instructions on contributing. Feel free to also report any issues or feature request in this repo.  

You can see the [roadmap](https://github.com/users/kevinslin/projects/3/views/1) to see upcoming changes. 

[^1]: NOTE: AWS Reference Notes currently has 66 services respresented