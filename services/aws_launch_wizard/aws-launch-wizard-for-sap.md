---
id: AWS Launch Wizard for SAP
title: AWS Launch Wizard for SAP
created: 1683841041000
updated: 1683841041000
---
# AWS Launch Wizard for SAP

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-launch-wizard-user-guide.git)
{% endhint %}

## Make SAP HANA software available to Launch Wizard

- **Note**  
We recommend that you place only the main SAP HANA installation files in the S3 bucket\. Do not place multiple SAP HANA versions in the same folder\. SAP provides the software as a single \.zip file or as multiple files depending on the SAP HANA version \(one \.exe file and multiple \.rar files\)\. Upload them to the version\-specific folder that you created\.


## Make SAP application software available to Launch Wizard

- **Note**  
The software versions and CD numbers listed in the following table should be used as a reference for all of the software components required to deploy SAP, as well as for how to format the Amazon S3 path to make the software available for Launch Wizard to deploy SAP\. Launch Wizard supports NetWeaver 7\.50, NetWeaver 7\.52, S/4 HANA 1909, S/4 HANA 2020, and BW/4HANA 2\.0\. You can determine the latest CD numbers of supported applications by referring to the [SAP Maintenance Planner](https://support.sap.com/en/alm/solution-manager/processes-72/maintenance-planner.html) or [SAP Software Downloads](https://support.sap.com/en/my-support/software-downloads.html)\.
- **Note**  
Use the latest CDs for the version\.
- **Note**  
Use the latest CDs for the version\.
- **Note**  
\*Use the latest CDs for the version\.
- **Note**  
\*Use the latest CDs for the version\.
- **Note**  
\*Use the latest CDs for the version\.
- **Note**  
\*Use the latest CDs for the version\.
- **Note**  
\*Use the latest CDs for the version\.
- **Note**  
Use the latest CDs for the version\.


## Scale SAP applications after initial deployment

- **Note**  
You can only delete a node that was created with the add or remove node feature using Launch Wizard for SAP\.
- **Note**  
You can only delete a node that was created with the add or remove node feature using Launch Wizard for SAP\.


## Deploy SAP applications using proxy server

- **Note**  
Include the hostnames of ASCS, ERS, primary SAP HANA, and secondary SAP HANA instances in the *No proxy setting \- optional* field, if you are deploying an SAP system with high availability using RHEL operating system\. This will enable the cluster to communicate with all the nodes as well as perform any failover or failback operations\.
- **Note**  
The troubleshooting steps are only applicable to the Squid proxy server\. The location of the `log` file varies with the type of proxy server\.


## Security groups

- **Note**  
When the deployment is complete, you can update the security group information by adjusting the port range and source information\.
- **Note**  
Launch Wizard considers a security group that it created as a shared resource\. It does not delete the security group if you delete a deployment or if a deployment is rolled back\.

