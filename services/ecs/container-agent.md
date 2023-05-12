---
id: Container agent
title: Container agent
created: 1683841041000
updated: 1683841041000
---
# Container agent
## Installing the Amazon ECS container agent

- **Note**  
The `systemd` units for both Amazon ECS and Docker services have a directive to wait for `cloud-init` to finish before starting both services\. The `cloud-init` process is not considered finished until your Amazon EC2 user data has finished running\. Therefore, starting Amazon ECS or Docker via Amazon EC2 user data may cause a deadlock\. To start the container agent using Amazon EC2 user data you can use `systemctl enable --now --no-block ecs.service`\.
- **Note**  
If you get no response, ensure that you associated the Amazon ECS container instance IAM role when launching the instance\. For more information, see [Amazon ECS container instance IAM role](instance_IAM_role.md)\.
- **Note**  
When using a non\-Amazon Linux AMI, your Amazon EC2 instance requires `cgroupfs` support for the `cgroup` driver in order for the Amazon ECS agent to support task level resource limits\. For more information, see [Amazon ECS agent on GitHub](https://github.com/aws/amazon-ecs-agent)\.


## Container agent versions

- **Note**  
As new Amazon ECS\-optimized Amazon Linux 2 AMIs and Amazon ECS agent versions are released, older versions are still available for launch in Amazon EC2\. However, we encourage you to [update to the latest version](ecs-agent-update.md) of the Amazon ECS agent and to keep your container instance software up to date\. If you request support for an older version of the Amazon ECS agent through AWS Support, you may be asked to move to the latest version as a part of the support process\.
- **Important**  
Amazon ECS agent versions 1\.20\.0 and later have deprecated support for Docker versions older than 1\.9\.0\.
- **Note**  
As new Amazon ECS\-optimized Amazon Linux AMIs and Amazon ECS agent versions are released, older versions are still available for launch in Amazon EC2\. However, we encourage you to [update to the latest version](ecs-agent-update.md) of the Amazon ECS agent and to keep your container instance software up\-to\-date\. If you request support for an older version of the Amazon ECS agent through AWS Support, you may be asked to move to the latest version as a part of the support process\.
- **Important**  
Amazon ECS agent versions 1\.20\.0 and later have deprecated support for Docker versions older than 1\.9\.0\.


## Updating the Amazon ECS container agent

- **Note**  
Agent updates do not apply to Windows container instances\. We recommend that you launch new container instances to update the agent version in your Windows clusters\.
- **Note**  
The introspection API added `Version` information in the version v1\.0\.0 of the Amazon ECS container agent\. If `Version` is not present when querying the introspection API, or the introspection API is not present in your agent at all, then the version you are running is v0\.0\.3 or earlier\. You should update your version\.


## Container agent configuration

- **Note**  
For a full list of available Amazon ECS agent configuration variables, see [Amazon ECS Container Agent](https://github.com/aws/amazon-ecs-agent/blob/master/README.md) on GitHub\.


## Private registry authentication for container instances

- **Important**  
We do not recommend that you inject these authentication environment variables at instance launch with Amazon EC2 user data or pass them with the `--env` option to the docker run command\. These methods are not appropriate for sensitive data, such as authentication credentials\. For information about safely adding authentication credentials to your container instances, see [Storing container instance configuration in Amazon S3](ecs-agent-config.md#ecs-config-s3)\.
- **Important**  
Newer versions of Docker create a configuration file as shown above with an outer `auths` object\. The Amazon ECS agent only supports `dockercfg` authentication data that is in the below format, without the `auths` object\. If you have the jq utility installed, you can extract this data with the following command: cat \~/\.docker/config\.json \| jq \.auths
- **Important**  
If the previous command does not return the `ECS_DATADIR` environment variable, you must stop any tasks running on this container instance before stopping the agent\. Newer agents with the `ECS_DATADIR` environment variable save their state and you can stop and start them while tasks are running without issues\. For more information, see [Updating the Amazon ECS container agent](ecs-agent-update.md)\.


## Automated task and image cleanup

- **Note**  
The Amazon ECS agent image pull behavior can be customized using the `ECS_IMAGE_PULL_BEHAVIOR` parameter\. For more information, see [Amazon ECS container agent configuration](ecs-agent-config.md)\.
- **Note**  
The automated image cleanup feature requires at least version 1\.13\.0 of the Amazon ECS container agent\. To update your agent to the latest version, see [Updating the Amazon ECS container agent](ecs-agent-update.md)\.


## Task metadata endpoint

- **Important**


## Container agent endpoint

- **Important**
- **Note**  
You can add support for this feature on Amazon EC2 instances using older versions of the Amazon ECS container agent by updating the agent to the latest version\. For more information, see [Updating the Amazon ECS container agent](ecs-agent-update.md)\.


## Container agent introspection

- **Important**  
Your container instance must have an IAM role that allows access to Amazon ECS in order to retrieve the metadata\. For more information, see [Amazon ECS container instance IAM role](instance_IAM_role.md)\.
- **Note**  
Amazon ECS container agents before version 1\.14\.2 require full Docker container IDs for the introspection API, not the short version that is shown with docker ps\. You can get the full Docker ID for a container by running the docker ps \-\-no\-trunc command on the container instance\.


## Using gMSAs for Windows Containers

- **Note**  
This feature is not supported on Windows containers on Fargate\.


## Using gMSAs for Linux Containers

- **Note**  
This feature is not supported on Fargate\. For Linux on Fargate, you can follow the example [Using Windows Authentication with Linux Containers on Amazon ECS](http://aws.amazon.com/blogs/containers/using-windows-authentication-with-linux-containers-on-amazon-ecs/)\.
- **Note**  
If you chose to use your own KMS key to encrypt your secret, then you must add the necessary permissions to this role and add this role to the AWS KMS key policy\.


## Updating the Amazon ECS container agent with the console

- **Note**  
Agent updates do not apply to Windows container instances\. We recommend that you launch new container instances to update the agent version in your Windows clusters\.

