---
title: "Data Access Governance RBAC Permissions"
slug: "data-access-governance-rbac-permissions"
updated: 2026-09-30T08:42:37Z
published: 2026-09-30T08:42:37Z
canonical: "helpcenter.securiti.ai/data-access-governance-rbac-permissions"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Data Access Governance RBAC Permissions

The new Role-Based Access Control (RBAC) framework provides fine-grained permissions for Data Access Governance. Custom roles can include permissions that are linked to other related permissions, creating dependencies and ensuring consistent access control.

## Accessing Data Access Governance and Policy Engine Permissions

To access the Data Access Governance and Policy Engine RBAC permissions in Securiti Platform, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Settings** from the left navigation bar.

![RBAC_settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3446953a-4ab3-9974-83d0-7024b42ca2cb.png)
2. Under the **Organizational**, choose **Access Management > Roles**.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled%202(16).png)
3. On the **Roles** page, select **+ Create Role**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Untitled 3(13).png)
4. Under the **Permissions** section, click the **Settings** tab to access Data Access Governance and Policy Engine permissions, as shown below.

![DAG_RBAC_Access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a7e3b23-39a3-de81-9501-3d0e3553643e.png)

### Data Access Governance Permissions with default roles

The only out of the box role which provides Data Access Governance permissions is **Super Admin**. All the other use of Data Access Governance requires custom roles with permissions granted for this functionality.

| Permission | Super Admin | Organization Admin | MODULE OWNER | DPO | USER | Operator | SDI Analyst | SDI Evidence Analyst | SDI Classification Reviewer | Discovery Scan Manager | Data Classification Manager | MODULE OWNER Data Breach User Profile ROLE | MODULE OWNER Self Service Portal User Profile ROLE | GUEST Self Service Portal User Profile ROLE | MODULE OWNER Data map User Profile ROLE | USER DSR User Profile ROLE | DATA USER | GUEST Data map User Profile ROLE | USER Data map User Profile ROLE | USER Self Service Portal User Profile ROLE | MODULE OWNER DSR User Profile ROLE | GUEST DSR User Profile ROLE |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `Execute Access Scan Definitions` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Access Scan Definitions` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Data Access Governance Dashboards` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage IAM Metadata Sources` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Access Scan Definitions` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Data Access Intelligence` | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

> [!NOTE]
> **Note**
> 
> This table shows which **Policy Engine** permissions are allowed or restricted for each default role. Note that the **Policy Engine** Permissions are required to perform actions related to **Data Access Control Policies** and **Cross Border Transfer Policies**.

### Policy Engine permissions with default roles

This table shows which data system permissions are allowed or disallowed for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| **Permission** | **Super Admin** | **Organization Admin** | **MODULE OWNER** | **DPO** | **USER** | **Operator** | **SDI Analyst** | **SDI Evidence Analyst** | **SDI Classification Reviewer** | **Discovery Scan Manager** | **Data Classification Manager** | **Gencore Reader** | **Provider Manager** | **Firewall Admin** | **Gencore Pipe Builder** | **Gencore Admin** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| View Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Manage Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ |
| View Automation Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned Automation Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Automation Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Manage Owned Automation Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |
| View Access Control Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned Access Control Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Access Control Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Owned Access Control Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Cross Border Transfer Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Cross Border Transfer Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Data Labeling Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned Data Labeling Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Data Labeling Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Owned Data Labeling Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View File Quarantine Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned File Quarantine Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage File Quarantine Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Owned File Quarantine Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View File Insights Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned File Insights Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage File Insights Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Owned File Insights Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View File ROT Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned File ROT Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage File ROT Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Owned File ROT Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View LLM Firewall Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned LLM Firewall Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage LLM Firewall Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Managed Owned LLM Firewall Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Metadata Registration Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned Metadata Registration Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Metadata Registration Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Owned Metadata Registration Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Security Posture Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Security Posture Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Structured Data Insights Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Owned Structured Data Insights Policies | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Structured Data Insights Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Manage Owned Structured Data Insights Policies | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ | ❌ | ✅ | ✅ | ✅ |
| View Data Remediation | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ |
| Manage Data Remediation | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ |
| View Policy Findings | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |
| View Policy Findings | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Update Policy Findings | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Manage Policy Findings | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| Export Policy Findings | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Manage Policy Templates | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| View Posture Rule | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ |
| Manage Posture and Test Rule | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ | ✅ |
| View Sensitivity Labels | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| Sync Sensitivity Labels | ✅ | ✅ | ✅ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |

### Data Access Governance Permissions with custom roles

Securiti lets you select fine-grained permission for each custom role you create in the Platform.

**Definitions**

- **Permission**: It is a parent permission that grants specific rights to perform certain actions within the system. For example, `Manage IAM Metadata Sources`, `Manage Access Scan Definitions`, and `Execute Access Scan Definitions`.
- **Explanation:** Describes why the permission is needed and the context in which it is used. For example, `Manage IAM Metadata Sources` permission is required to create and update an IAM Metadata Source..
- **Dependent permissions:** These are a set of permissions that are automatically applied in the same or different modules when a parent permission is selected.

This table lists the Data Access Governance permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| **Permission** | **Explanation** | **Dependent permissions** |
| --- | --- | --- |
| **View Access Scan Definitions** | This permission lets you access the Access Scan Definition page. You can see the list of existing Access Scan Definitions configured. You cannot Create an Access Scan Definition | • No dependent permission |
| **Manage Access Scan Definitions** | This permission lets you: • Access the Access Scan Definitions Page • View the list of configured Access Scan Definitions • Create an Access Scan Definition • Update an existing Access Scan Definition • Delete an Access Scan Definition | Data Access Governance: • View Access Scan Definitions Deployment: • [View My Deployments](/v1/docs/rbac-permissions-with-custom-roles#deployment-permissions) Data Systems • [Read Data System API](/v1/docs/rbac-permissions-with-custom-roles#data-systems-permissions) |
| **Execute Access Scans** | This permission lets you: • Access the Access Scan Definitions Page • View the list of configured Access Scan Definitions • Initiate an Access Scan You cannot create an Access Scan Definition. | Data Access Governance: • View Access Scan Definitions View IAM Metadata Sources |
| **View IAM Metadata Sources** | This permission lets you access IAM Metadata Sources and you can see the list of the IAM Metadata sources configured. | • No dependent permission |
| **Manage IAM Metadata Sources** | This permission lets you: • Access IAM Metadata Sources Page • View the list of configured Metadata Sources • Create an IAM Metadata Source • Update an existing Metadata Source • Delete an IAM Metadata Source | Data Access Governance: • View IAM Metadata Sources Deployment: • [View My Deployments](/v1/docs/rbac-permissions-with-custom-roles#deployment-permissions) Data Systems • [Read Data System API](/v1/docs/rbac-permissions-with-custom-roles#data-systems-permissions) |
| **Manage Data Access Governance Dashboards** | This permission lets you access, view, and manage data access intelligence related information on following dashboards: • Data Command Graph • Graph Explorer • Access Graph Explorer • Over-Privileged Users • Most Active Users • Reporting Dashboards You can Create and Save a new filter on the dashboards, and also create new widgets or dashboards for reporting purposes. | Data Access Governance • View Data Access Intelligence Securiti Platform: • Create Saved Filter • Update Saved Filter • Delete Saved Filter Sensitive Data Intelligence: • View Data Elements Data Command Center: • View Graph Explorer Page • View Reporting And Dashboards • Manage Reporting And Dashboards |
| **View Data Access Intelligence** | This permission lets you access, view, and manage data access intelligence related information on following dashboards: • Data Command Graph • Graph Explorer • Access Graph Explorer • Over-Privileged Users • Most Active Users • Reporting Dashboards You can Create and Save a new filter on the dashboards, but you cannot create new widgets or dashboards for reporting purposes. | Securiti Platform: • Create Saved Filter • Update Saved Filter • Delete Saved Filter Sensitive Data Intelligence: • View Data Elements Data Command Center: • View Graph Explorer Page • View Reporting and Dashboards |

### Policies permissions with custom roles

> [!NOTE]
> **Note**
> 
> This table shows which **Policy Engine** permissions are allowed or restricted for each custom role. Note that the **Policy Engine** Permissions are required to perform actions related to **Data Access Control Policies** and **Cross Border Transfer Policies**.

This table lists the Policy Engine permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent permissions |
| --- | --- | --- |
| **View Access Control Policies** | This permission lets you access the Access Control Policies page and view the list of configured access control policies, which control and restrict who can access sensitive data in your data systems. You cannot create, update, or delete an Access Control Policy. | **Sensitive Data Intelligence:** - [View Content Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Dictionaries](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Document Categories And Types](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Indexes](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View File Formats](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) **Securiti Platform:** - [View Private Cloud Storage](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Read Email Template](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Create Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) **Data Command Center:** - [View Reporting and Dashboards](/latest/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) |
| **View Owned Access Control Policies** | This permission lets you access the Access Control Policies page and view only the access control policies that you own. You cannot see policies owned by other users, and you cannot create, update, or delete an Access Control Policy. | **Sensitive Data Intelligence:** - [View Content Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Dictionaries](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Document Categories And Types](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Indexes](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View File Formats](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) **Securiti Platform:** - [View Private Cloud Storage](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Read Email Template](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Create Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) **Data Command Center:** - [View Reporting and Dashboards](/latest/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) |
| **Manage Access Control Policies** | This permission lets you: - Access the Access Control Policies page - View the list of configured access control policies - Create an Access Control Policy - Update an existing Access Control Policy - Delete an Access Control Policy | **Policy Engine:** - [View Access Control Policies](/latest/docs/policy-engine-rbac-roles-and-permissions#module-name-permissions-with-custom-roles) **Sensitive Data Intelligence:** - [View Content Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Dictionaries](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Document Categories And Types](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Indexes](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View File Formats](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) **Securiti Platform:** - [View Private Cloud Storage](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Read Email Template](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Create Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) **Data Command Center:** - [View Reporting and Dashboards](/latest/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) |
| **Manage Owned Access Control Policies** | This permission lets you: - Access the Access Control Policies page - View the access control policies that you own - Create an Access Control Policy - Update an Access Control Policy that you own - Delete an Access Control Policy that you own You cannot update or delete policies owned by other users. | **Policy Engine:** - [View Access Control Policies](/latest/docs/policy-engine-rbac-roles-and-permissions#module-name-permissions-with-custom-roles) - [View Owned Access Control Policies](/latest/docs/policy-engine-rbac-roles-and-permissions#module-name-permissions-with-custom-roles) **Sensitive Data Intelligence:** - [View Content Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Dictionaries](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Document Categories And Types](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Indexes](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View File Formats](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) **Securiti Platform:** - [View Private Cloud Storage](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Read Email Template](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Create Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) **Data Command Center:** - [View Reporting and Dashboards](/latest/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) |
| **View Cross Border Transfer Policies** | This permission lets you access the Cross Border Transfer Policies page and view the list of configured cross border transfer policies, which monitor and control the movement of data across geographic and jurisdictional boundaries. You cannot create, update, or delete a Cross Border Transfer Policy. | **Sensitive Data Intelligence:** - [View Content Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Dictionaries](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Document Categories And Types](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Indexes](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View File Formats](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) **Securiti Platform:** - [View Private Cloud Storage](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Read Email Template](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Create Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) **Data Command Center:** - [View Reporting and Dashboards](/latest/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) |
| **Manage Cross Border Transfer Policies** | This permission lets you: - Access the Cross Border Transfer Policies page - View the list of configured cross border transfer policies - Create a Cross Border Transfer Policy - Update an existing Cross Border Transfer Policy - Delete a Cross Border Transfer Policy | **Policy Engine:** - [View Cross Border Transfer Policies](/latest/docs/policy-engine-rbac-roles-and-permissions#module-name-permissions-with-custom-roles) **Sensitive Data Intelligence:** - [View Content Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Dictionaries](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Document Categories And Types](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Profiles](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Exact Data Indexes](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View File Formats](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) - [View Data Elements](/latest/docs/sensitive-data-intelligence-roles-and-permissions#content-classification-permissions-with-custom-roles) **Securiti Platform:** - [View Private Cloud Storage](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Read Email Template](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Create Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Update Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) - [Delete Saved Filter](/latest/docs/securiti-platform-rbac-permissions-and-roles#securiti-platform-permissions-with-custom-roles) **Data Systems:** - [Read Data System API](/latest/docs/data-systems-rbac-permissions-and-roles#data-system-permissions-with-custom-roles) **Data Command Center:** - [View Reporting and Dashboards](/latest/docs/data-command-center-rbac-permissions-and-roles#data-command-center-permissions-with-custom-roles) |
