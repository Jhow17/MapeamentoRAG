---
title: "Using Data Access Control Policies"
slug: "access-control-policies"
updated: 2026-09-23T06:50:02Z
published: 2026-09-23T06:50:02Z
canonical: "helpcenter.securiti.ai/access-control-policies"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Using Data Access Control Policies

With Securiti's data access control policies, you have a centralized framework to manage authorization policies for your structured and unstructured data systems. You can enforce fine-grained access control policies around accessing a resource (file, folder, database, table, column etc) for a particular set of users and groups. Using access control policies, you can

- Securely share your sensitive data by implementing masking so that users can access only relevant data
- Enforce privilege conditions to maintain a least- privileged access model
- Enforce access policies based on insights into the underlying data, such as sensitivity, location of data, applicable regulations and more

You can centrally manage the access permissions for files, folders, databases, tables, and columns across your data systems using Data Access Control Policies. Data Access Control Policies page gives you complete visibility and control to create, filter, and manage policies centrally.

> [!NOTE]
> Note
> 
> If Data Access Control Policies are not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

### Creating Data Access Control Policies

Securiti lets you create Data Access Control Policies for both structured and unstructured data systems. To see the list of supported Data Systems for Access Control Policies, see [Data System Coverage for Data Access Governance](/v1/docs/data-access-governance-dag-overview#data-system-coverage-for-data-access-governance).

To configure the Data Access Control Policies for the supported Data Systems, see:

- [Databricks](/v1/docs/databricks)
- [Snowflake](/v1/docs/data-access-governance-snowflake)
- [GoogleBigQuery](/v1/docs/google-bigquery)
- [Microsoft 365 SharePoint Online](/v1/docs/microsoft-365-sharepoint-online)
- [Apache Hive](/v1/docs/data-access-governance-apache-hive)
- [Apache Trino](/v1/docs/apache-trino)
- [Apache Presto](/v1/docs/apache-presto)
- [HDFS](/v1/docs/hdfs)
- [HDFS Google Data proc](/v1/docs/hdfs)
- [Starburst (Apache Ranger Driven Policies)](/v1/docs/starburst)

### Access Control Policies Preview and States

You can Preview the changes the policy will make to the access configurations of your data systems prior to the enforcement of the policy. Whenever you create, update, or delete a Data Access Control Policy for a Data System for which Policy Preview is supported, Securiti creates backups automatically, and you can restore to any backup to roll back to that specific state. These controls let you enforce the data access control policies on your data systems in a secure manner, ensuring that you realize the impact of the policies before enforcement.

Policy Preview presents you with the entities such as Databases, Tables, Columns, etc., and privileges, row filters, and masking functions that will be implemented upon successful enforcement of the policy. Note that the policy execution will start only if you **Accept** the Policy Preview.

Securiti supports the following systems for Policy Preview:

- Databricks
- Snowflake
- Google BigQuery

#### Policy Evaluation States

Securiti automatically evaluates and updates Access Control Policies based on changes in data systems, metadata, and access relationships. These system-driven events ensure that policy states remain accurate without manual intervention.

**Evaluation on Data Changes**

Policy evaluation is triggered when changes occur in the associated data system.

- If a data system is deleted, associated policies transition to **Not In Use**.
- Policies are no longer evaluated or executed on deleted data systems.

**Evaluation on Discovery Scan**

When a **Discovery Scan** completes, the system updates policies associated with the scanned data system.

- Policies are re-evaluated using the latest discovered assets.
- For preview-supported systems, the policy transitions to **Preview Ready** after successful evaluation.
- Updated entities such as databases, tables, or columns are reflected in the preview.

**Evaluation on Access Graph Updates**

When access relationships are updated in the system, policies are re-evaluated automatically.

- Changes in users, roles, or permissions trigger re-evaluation.
- The system updates policy results based on the latest access relationships.
- Policies may transition between states such as **Evaluating**, **Preview Ready**, or **Failed in Evaluation** depending on the outcome.

**State Transitions**

Based on evaluation outcomes, policies transition between states:

- **Evaluating → Preview Ready**: Preview generated successfully
- **Evaluating → Failed in Evaluation**: Evaluation failed due to an error
- **Preview Ready → Preview Executed**: User accepts the preview
- **Evaluated → Not In Use**: Data system is no longer available

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 14(4).png)

#### Access Policy States for Non Preview based Data Systems

Policy states are the stages an Access Control Policy goes through before being enforced on the selected target data system.

Non Preview based data systems are the data sources for which Securiti does not generate Policy Preview. The Policy after creation is evaluated by the system and applied on the selected Data System. The tables below shows the Policy States for Non Preview based Data Systems.

| Policy State | Description |
| --- | --- |
| Created | Policy has been created without activation, and is not yet applied on the Data System. |
| Evaluating | Policy evaluation is in progress. The defined policy rules are being translated before being forwarded to the Pod. |
| Evaluated | Policy evaluation is complete, and sent to the Pod. |

#### Access Policy States for Preview based Data Systems

Preview based data systems are the data sources for which Securiti generates Policy Preview.

The tables below shows the Policy States for Preview based Data Systems.

| Policy State | Description |
| --- | --- |
| Created | Policy has been created without activation, and is not yet applied on the Data System. |
| Generating Preview | Preview is being generated after policy activation. |
| Preview Ready | Preview has been generated and ready to be accepted |
| Failed In Preview Generation | Policy Preview could not be generated |
| Preview Rejected | User rejected the generated Preview. |
| Graph Not Ready | Data Command Graph is not ready for processing. |
| Preparing for Execution | The system is preparing to apply the policy. Preparing Payload for evaluation. |
| Evaluating for Execution | The system is validating before applying the policy. Evaluating the preview before executing on the data system. |
| Executing Preview | Preview execution is in progress on the data system. |
| Preview Executed | User accepted the Preview, Policy applied to the Data system. |
| Not In Use | Data system instance is deleted; Policies in Evaluated State transition into “Not in use.” |

### Viewing Data Access Control Policies

The Data Access Control Policies page provides you a single view of all defined policies along with their current states and owners. To view Access Control Policies:

- In Securiti, near the upper left corner, click the jewel icon, and choose **Policies**
- From the left panel, choose **Data Access Control**

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 15(4).png)

You can sort the list of policies using the Search bar or by applying filters.

- Search by **Policy Name**: Quickly find a policy by typing part or all of its name.
- **Apply Filters:** Click on **+** icon , to apply Filters to sort Policies by:
  - Data Scope (Databrick, Google BigQuery, Snowflake, etc.)
  - Owner (policy owner’s initials)
  - Policy ID (numeric identifier)
  - Status (active or inactive)

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 16(1).png)

The grid displays each policy as a row with the following details:

- Status: Toggle to enable or disable the policy.
- Policy ID: Unique identifier assigned to the policy.
- Policy Name: A descriptive name of the policy that you defined while creating the policy.
- Data Scope: Indicates the selected system on which the policy applies (Active Directory, BigQuery, Snowflake, Microsoft 365 SharePoint, etc.).Policy scope (Entities such as Tables, Columns, Folders, User Groups, etc.)
  - Policy scope (Entities such as Tables, Columns, Folders, User Groups, etc.) displayed as blue chips.
- State: Indicates the lifecycle stage of the policy (e.g., Created, Evaluated, Preview Ready). States are displayed as green chips.
- Owner: Shows the initials of the policy owner.

**Click Options (Three dots) (⋮)** which provide options to:

- View: Inspect the policy details.
- Edit: Modify existing configurations.

| Category | Policy State |
| --- | --- |
| Editable States(Policies can be edited) | Created |
| Evaluated |
| Failed In Evaluation |
| Failed In Preview Generation |
| Preview Rejected |
| Preview Executed |
| Graph Not Ready |
| Non-Editable States(Policies cannot be edited) | Evaluating |
| Generating Preview |
| Preparing for Execution |
| Evaluating for Execution |
| Executing Preview |
| Not In Use |
| Preview Ready |
- Clone: Duplicate a policy for reuse.
- Delete: Remove the policy from the system. To see these steps in action, watch the video below:

## Demo : Configuring Data Access Control Policies for Google BigQuery

Access Control Policies give you a centralized framework to enforce fine-grained restrictions based on data classification across your connected data systems, ensuring only the right users access sensitive data. For Google BigQuery, this includes Column Masking, Row Filtering, and Permissions Management at the table and column level. You can allow or deny access to columns using the Fine-Grained Reader role, define masking rules using the Masked Reader role, and restrict row-level access by configuring row filters on tables for specific principals. This demo walks through creating an Access Control Policy for Google BigQuery, configuring its scope and rules, previewing the policy's impact, and applying it with automatic backup and rollback support.
