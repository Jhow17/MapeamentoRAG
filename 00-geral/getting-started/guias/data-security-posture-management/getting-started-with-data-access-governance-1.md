---
title: "Getting Started with Data Access Governance"
slug: "getting-started-with-data-access-governance-1"
updated: 2026-10-07T09:40:58Z
published: 2026-10-07T09:40:58Z
canonical: "helpcenter.securiti.ai/getting-started-with-data-access-governance-1"
area: geral
modulo: getting-started
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Data Access Governance

This section describes the Data Access Governance module feature sets and configuration process.

[Embedded object](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/DAG-flowchart.svg)

## Data Access Governance Prerequisites

Following are the prerequisites that need to be configured for using the Data Access Governance feature sets:

### Step 1 - Set up the Pod

Set up the Pod which you will use to perform different types of scans on your data systems. For more information, see [Pods documentation](/v1/docs/securiti-pods-and-elastic-pods).

### Step 2 - Configure the Data system Connectors

Configure and activate the data systems connector to connect your data systems with Securiti. This lets you integrate your data systems with Securiti platform and scan different types of metadata.

### Step 3 - Perform Data Inventory Sync or Discovery Scan

Data Inventory Sync collects high-level metadata for the self-hosted pod connectors to present you with the information such as file names, types, sizes, creation and modification dates, and other relevant properties. For more information, please refer to the Data Inventory Sync for data systems.

Perform Discovery Scans to discover and classify sensitive and personal information stored within your data systems. Securiti utilizes this information for providing you insights into the users that have access to your sensitive data. You can also use this information to restrict access of your users and user groups to sensitive and personal information stored in your data system using data access control policies. For more, see discovery scans documentation.

### Access Intelligence

Access Intelligence provides insight into the users’ access to applications and data.

### Step 4 and Step 5 - Configure IAM Metadata Sources and Access Scan Definition

To see the Privilege and Activity Analysis data, you must configure IAM Metadata Sources and Access Scan Definition.

| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WD6JGPMQ.png) | **Configure an IAM Metadata Source** IAM Metadata sources provides authentication and connectivity to your data systems and policy or identity metadata for systems like Apache Ranger in order to enable Access Intelligence [Learn more](/latest/docs/iam-metadata-sources) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-X041AS0Y.png) | **Create an Access Scan Definition** Access Scan Definitions allow you to configure Data Access Intelligence Scans of your data systems enabling the gathering of Identity and Access Management (IAM) and Role Based Access Control (RBAC) metadata [Learn more](/latest/docs/access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources) |

### Step 6 - Perform Access Scan

Perform Access Scan to get the metadata related to privileges . On the Access Scan Definition page, activate the Access Scan Definition that you created. This lets you scan your data systems for IAM and RBAC metadata.

[Learn more](/latest/docs/access-scan-definitions)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-095F37SJ.png)

### Step 7 - Perform Activity Analysis Scan

On the Access Scan Definition page, activate the Access Scan Definition that you created using a metadata source for Activity Analysis.

[Learn more](/latest/docs/access-intelligence-scans-using-access-scan-definitions-and-iam-metadata-sources)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-17U44HRQ.png)

## Access Intelligence for Cloud Accounts Onboarded by IaaS Connectors

Securiti also provides visibility into the privileges and permissions that your users have on data sources within IaaS accounts.

| **Select the IaaS Cloud Connector to onboard** Select the IaaS Cloud Connector to onboard. This helps you integrate your cloud account with Securiti platform. [Learn more](/latest/docs/getting-started-with-iaas-cloud#accessing-the-iaas-cloud-module) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-2UVOM4T1.png) |
| --- | --- |
| **Select the Scan Location (**Securiti **Cloud or My Cloud) and Configure Settings** Securiti lets you choose the location where the scanning must be performed. You need to provide the following information: - Scan Location - Region [Learn more](/latest/docs/getting-started-with-iaas-cloud#step-2-specify-the-scan-location) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(44).png) |
| **Specify the types of Scans you want to perform** Select the types of scan you want to perform. For Privilege Analysis, you must perform the following scans - Asset Discovery - To discover assets within your IaaS cloud environment. - Access Entitlements scan - To discover permissions and privileges on the data sources [Learn more](/latest/docs/getting-started-with-iaas-cloud#step-3-select-the-scans-to-perform) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LPY534N4.png) |
| **View Results** View the permissions, privileges, and users' access to data in Data Command Graph and Identity Graph Explorer. | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-7NHQBGDB.png) |

## Review Data Access Privileges and Activity

You can view the relevant results in the Data Command Graph, Activity Explorer and Access Graph Explorer.

| [Embedded content](https://player.vimeo.com/video/949054606) | **Data Command Graph** View the detailed insights about the access patterns, configurations and explore the relationship between different entities. [Learn more](/latest/docs/data-command-graph) |
| --- | --- |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled(19).png) | **Access Graph Explorer** Use built-in queries in the Access Graph Explorer to identify the users, groups, and roles that can access sensitive data. [Learn more](/latest/docs/understanding-graph-explorer) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/creating_widget_1(1).png) | **Build Reports and Dashboards with Graph Queries** Build fully customized reports and dashboards to visualize and report access data as per your requirement. [Learn more](/latest/docs/creating-widgets-in-graph-explorer) |
| ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 2(7).png) | **Review Access Activity** Review the activities performed by your users in the data systems using Activity Explorer. [Learn more](/latest/docs/starburst#activity-analysis) |

## Cross Border Data Transfer

You can manage cross-border data transfer policies to get alerts and recommendations for the illegal cross-border transfer. Cross-border transfer policies can be developed to incorporate a wide range of embedded global regulatory insights, enabling the analysis of data access scenarios that might result in compliance breaches.

> [!NOTE]
> Note
> 
> Cross Border Data Transfer Policies utilize the metadata gathered from Activity Analysis. Therefore, it is mandatory to configure Activity Analysis for a data system to receive alerts for your cross border data transfers using policies.

| **Define Data Subject Types in Data Mapping Automation Module** Define Data Subject Types, e.g. employees, job applicants, prospects, partners, etc. for the data asset asset in the data mapping automation module. See creating and editing data subjects. [Learn more](/latest/docs/creating-and-editing-data-assets) | ![Data_subject_types.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f4528c11-326b-ffab-710a-62d9bfe734b8.png) |
| --- | --- |
| **Define Data Mapping Institute with Primary and Secondary Entities** Create an institute in Data Mapping and Automation module, and define primary and secondary entities. [Learn more](/latest/docs/creating-and-editing-institutions) | ![Institute.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d169606d-52b8-fd69-9c4e-412caab78bda.png) |
| **Edit Cross border Transfer Policies** Edit Cross Border Data Transfer Policies’ response section as per requirement. [Learn more](/latest/docs/using-cross-border-transfer-policies) | ![Cross_Border_policies.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-1762496401887.png) |
| **View Findings** View the alerts and recommendations on the Findings page for possible illegal cross-border transfer. You can view metrics for **Open Findings**, and count for **Fixed** and **Suppressed Findings**. | ![Findings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-07cf8ecb-da21-d337-1312-90db8c0320e8.png) |

## Access Control Policies

You can define cross-border data transfer policies to restrict access of your users and groups to the sensitive data within your data systems. You can also apply dynamic masking conditions to selectively show the sensitive data to only authorized users

| **Enable Access Control Policies in Data system Connectors** Mark the **Enable Access Control** option in the relevant Data System Connector page for defining the policies for your data system instance. [Learn more](/latest/docs/data-access-control-policies) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-DE9JXNSG.png) |
| --- | --- |
| **Define Access Control Policies** You can define Access Control Policies to restrict the access of your users and groups to the sensitive data. You can restrict rows access to data rows based on specific conditions. This method is essential for protecting sensitive data and ensuring that only authorized users can access specific subsets of data. [Learn more](/latest/docs/data-access-control-policies) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-07HLIFK9.png) |
| **Access Policy Preview and Backup** You can Preview the changes the policy will make to the access configurations of your data systems prior to the enforcement of the policy. For each of the policy, that you create, update, or delete, Securiti creates backups automatically, and you can restore to any backup to roll back to that specific state. [Learn more](/latest/docs/access-policy-preview-and-backup) | ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M4SWRTCP.png) |

## Data Access Governance Module API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details.

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-access-governance/apidocs/index.html). | ![DAG_API.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b7d6ad09-c64d-f1d9-6e9e-3f6574f8f7c8.png) |
| --- | --- |
| **Download the Postman collection** We also provide a Postman collection for customers who prefer using it to execute APIs. This collection contains a set of pre-configured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/data-access-governance/apidocs/index.html#section/Authentication). | ![DAG_Postman.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-113af51c-f7a7-17c5-a69a-df02a2c82147.png) |
