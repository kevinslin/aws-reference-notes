---
id: Tasks
title: Tasks
created: 1683841041000
updated: 1683841041000
---
# Tasks

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-dms-user-guide.git)
{% endhint %}

## Continuous replication tasks

- **Note**  
You can migrate views using full\-load tasks only\. If your task is either a CDC\-only task or a full\-load task that starts CDC after it completes, the migration includes only tables from the source\. Using a full\-load\-only task, you can migrate views or a combination of tables and views\. For more information, see [ Specifying table selection and transformations rules using JSON](CHAP_Tasks.CustomizingTasks.TableMapping.SelectionTransformation.md)\.
- **Note**  
AWS DMS bidirectional replication isn't intended as a full multi\-master solution including a primary node, conflict resolution, and so on\.
- **Note**  
Only one task in a bidirectional pair can be full load and CDC\.
- **Note**  
When using the AWS CLI, use only the `create-replication-task` or `modify-replication-task` commands to configure `LoopbackPreventionSettings` in your bidirectional replications tasks\.


## Moving a task

- **Note**  
You can't move a task to the same replication instance where it currently resides\.
You can't modify the settings of a task while it's moving\.
A task you have run must have a status of **Stopped**, **Failed**, or **Failed\-move** before you can move it\.


## Table mapping

- **Note**  
When working with table mapping for a MongoDB source endpoint, you can use filters to specify data that you want replicated, and specify a database name in place of the `schema_name`\. Or, you can use the default `"%"`\.


## Enabling and working with premigration assessments

- **Note**  
If you do a premigration assessment run that includes the data type assessment, you don't need to do a data type assessment separately\.

