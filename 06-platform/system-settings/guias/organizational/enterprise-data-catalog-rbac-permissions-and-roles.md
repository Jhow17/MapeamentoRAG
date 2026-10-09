---
title: "Enterprise Data Catalog RBAC permissions and roles"
slug: "enterprise-data-catalog-rbac-permissions-and-roles"
updated: 2026-09-21T21:00:02Z
published: 2026-09-21T21:00:02Z
canonical: "helpcenter.securiti.ai/enterprise-data-catalog-rbac-permissions-and-roles"
area: platform
modulo: system-settings
tipo: guia
data_captura: 2026-10-08
---

# Enterprise Data Catalog RBAC permissions and roles

The new Role-Based Access Control (RBAC) framework provides fine-grained permissions for Enterprise Data Catalog. It introduces a set of system-generated roles with predefined permissions, while also allowing you to create custom roles with Enterprise Data Catalog–specific permissions. Custom roles can include permissions that are linked to other related permissions, creating dependencies and ensuring consistent access control. In contrast, system-generated roles automatically inherit the specific permissions defined for them.

- [Accessing Enterprise Data Catalog permissions](/docs/enterprise-data-catalog-rbac-permissions-and-roles#accessing-module-name-permissions)
- [Enterprise Data Catalog permissions with default Roles](/docs/enterprise-data-catalog-rbac-permissions-and-roles#module-name-permissions-with-default-roles)
- [Enterprise Data Catalog permissions with custom roles](/docs/enterprise-data-catalog-rbac-permissions-and-roles#module-name-permissions-with-custom-roles)

### Accessing Enterprise Data Catalog permissions

To navigate to Enterprise Data Catalog RBAC permissions in Securiti, follow the steps provided below:

1. From the upper left corner of the left navigation bar, click the ​**Jewel**​ icon, and choose ​**Settings**​​. ![Settings page displaying organization details, domains, and advanced invite controls options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Settings.png)
2. Under the **​Organizational**​, choose ​**Access Management** **>** **Roles**​. ![System settings overview highlighting access management roles and organization details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Settings-Roles.png)
3. On the ​**Roles**​ page, select ​**+ Create Role​**.

![Overview of user roles and permissions in the system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create role.png)
4. From the ​**Permissions**​ section, click the ​**Enterprise Data Catalog** tab to access the permissions, as shown below. ![Creating a role with permissions including Enterprise Data Catalog in system settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Roles-EDC.png)

### Enterprise Data Catalog permissions with default Roles

This table shows which Enterprise Data Catalog permissions are allowed or restricted for each system-generated role. A check mark (✅) indicates allowed access, while a cross (❌) represents no access.

| Permission | DISCOVERY SCAN MANAGER | DPO | MODULE OWNER | OPERATOR | ORGANIZATION ADMIN | PROVIDER MANAGER | SDI ANALYST | SDI CLASSIFICATION REVIEWER | SDI EVIDENCE ANALYST | USER |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `Create Data Quality Checkpoint` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Data Quality Checkpoint` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Execute Data Quality Checkpoint` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Data Quality Checkpoint` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Quality Checkpoint` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Data Quality Expectation` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Data Quality Expectation` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Data Quality Expectation` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Quality Expectation` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Data Quality Finding` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Data Quality Finding` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Data Quality Finding` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Quality Finding` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Data Quality Template` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Data Quality Template` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Data Quality Template` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Quality Template` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Data Quality Template Type` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Data Quality Template Type` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Data Quality Template Type` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Quality Template Type` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Assertions` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Assertions` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Assertions` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Batch Soft Delete Charts` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Chart` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Chart` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Chart Deprecation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Chart Embed Information` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Charts` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Chart Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Chart Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Chart Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Chart Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Chart Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Chart Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Chart Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Chart Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Chart Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Chart Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Chart` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Chart Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Chart Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Container` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Container` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Containers` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Container Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Container Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Container Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Container Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Container` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Container Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Container Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Group` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Password Reset Token` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Group Contact Information` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Group Members` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit User Contact Information` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit User Profile` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manager User Credentials` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Users &amp; Groups` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Group` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove User` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Group Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Group Members` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Group Name` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update User Setting` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update User Status` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Groups` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Users And Groups Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Glossary Custom Relationship Type` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Glossary Custom Relationship Type` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Glossary Custom Relationship Types` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Custom Relationship Type` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Glossary Custom Relationship Type Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Batch Soft Delete Dashboards` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Dashboard` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Dashboard` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dashboard Deprecation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dashboard Embed Information` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Dashboards` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Dashboard Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Dashboard Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dashboard Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dashboard Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Dashboard` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Dashboard Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Dashboard Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Batch Soft Delete DataFlows` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Dataflow` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Dataflow` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataflow Deprecation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Dataflows` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Dataflow Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Dataflow Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataflow Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataflow Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataFlow Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataFlow Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataFlow Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataFlow Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataFlow Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataFlow Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataFlow Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View DataFlow` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View DataFlow Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View DataFlow Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Policy` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Policy` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Policies` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Policy` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Policy` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Secret` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Secret` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Secrets` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Secrets Metadata` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create View` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete View` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Global Views` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Personal Views` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Global Views Settings` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update View` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Global Views` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Batch Soft Delete DataJobs` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create DataJob` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete DataJob` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit DataJob Deprecation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage DataJobs` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove DataJob Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove DataJob Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit DataJob Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update DataJob Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View DataJob` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View DataJob Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View DataJob Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Manage Data Platforms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Data Platform Instances` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Data Platform Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Data Platform Instance Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Edit Data Process Instance Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Data Process Instance Groups` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Batch Soft Delete Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Import Data Product` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Data Product` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Data Product` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Export Data Product Assets` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Data Product Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Data Product Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Governance Status` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Link` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Name` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Owner` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Data Product Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Data Product Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Data Product Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Data Products` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Data Product Assets` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Batch Add Schema Metadata` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Batch Soft Delete Datasets` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Batch Soft Delete Queries` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Import Dataset` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Dataset` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Dataset Query` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Delete Dataset` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Dataset Query` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Column Descriptions` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Column Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Column Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Column Governance Flag` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Column Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Deprecation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Queries` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Embed Information` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Entity Operations` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Read-Only Status` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Data Product Read-Only Status` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Glossary Node Read-Only Status` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Glossary Term Read-Only Status` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Export Dataset` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Datasets` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Dataset Query` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Dataset Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Dataset Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Governance Status` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Query` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Dataset Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Dataset` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Dataset Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Dataset Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Dataset Profile` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Dataset Usage` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Queries` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Batch Soft Delete Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Domain` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Domain` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Domain Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Domain Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Domain Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Domain Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Domain Link` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Domain Name` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Domain Owner` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Move Domain` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Domain Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Domain` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Domain Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Add Related Nodes to Glossary Nodes` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Add Related Terms to Glossary Nodes` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Glossary Node` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Glossary Node` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Glossary Nodes` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Glossary Node Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Related Nodes from Glossary Node` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Related Terms from Glossary Node` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Glossary Node Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Domain` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Governance` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Governance Flag` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Name` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Owner` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Move Glossary Node` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Node Structured Subtype` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Glossary Nodes` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Glossary Node Audit` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Glossary Node Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Add Related Nodes to Glossary Term` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Add Related Terms to Glossary Term` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Batch Soft Delete Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Bulk Glossary Export` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Bulk Glossary Import` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Clone Glossary Term` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Glossary Term` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Glossary Term` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Mark Glossary Term Deprecated` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Glossary Term Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Related Nodes From Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Related Terms From Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove Glossary Term Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Custom Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Domain` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Governance` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Governance Flag` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Link` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Name` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Owner` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Move Glossary Term` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Structured Property` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Glossary Term Subtype` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Glossary Terms` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Glossary Term Audit` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Glossary Term Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Cancel Ingestion` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Run Ingestion` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Ingestion Source` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Ingestion Source` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Metadata Ingestion` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Rollback Ingestion` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Ingestion Source` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Ingestion` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Ingestion Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Edit Chart Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dashboard Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit DataFlow Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit DataJob Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Dataset Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit ML Feature Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit ML Feature Table Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit ML Model Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit ML Model Group Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit ML Primary Key Lineage` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create ML Feature` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete ML Feature` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage ML Feature Key` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Feature Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Feature Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Documentation Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Documentation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View ML Feature Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View ML Feature` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create ML Feature Table` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete ML Feature Table` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage ML Feature Table` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Feature Table Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Feature Table Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Documentation Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Documentation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Feature Table Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View ML Feature Table Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View ML Feature Table` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create ML Model` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete ML Model` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage ML Model` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Model Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Model Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Documentation Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Documentation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View ML Model Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View ML Model Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View ML Model` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create ML Model Group` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete ML Model Group` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage ML Model Group` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Model Group Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Model Group Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Documentation Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Documentation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Model Group Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View ML Model Group Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View ML Model Group` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create ML Primary Key` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete ML Primary Key` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage ML Primary Key` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Primary Key Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Remove ML Primary Key Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Custom Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Documentation Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Documentation` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Domains` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Glossary Terms` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update ML Primary Key Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View ML Primary Key Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View ML Primary Key` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Manage Notebook` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Edit Notebook Data Products` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Notebook Links` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Notebook Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Notebook Owners` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Notebook Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Notebook` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Notebook Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Ownership Type` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Ownership Type` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Global Ownership Types` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Ownership Type` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Ownership Types` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Global Announcements` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Global Announcements` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Home Page Posts` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Posts` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Accept Role` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Invite Token` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Roles` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Invite Token` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Roles` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Batch Soft Delete Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Structured Properties` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Structured Properties` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Structured Properties Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Generate Personal Tokens` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Get Analytics` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Get Entity Counts` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Get System Timeline` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Get Time Series Aspects` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Access Tokens` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Retention Policies` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Produce Platform Events` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Analytics` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Appliance List` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Data Sources` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Supported Connectors` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Tag` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Tag` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Tags` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Tag` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Tag Color` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Tag Description` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Tag Owner` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Tag` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Tag Audit` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Tag Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Test` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Delete Test` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Manage Tests` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Test` | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `View Test Details` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `View Test` | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| `Create Inferred Lineage` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Execute Inferred Lineage` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Inferred Lineage` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Inferred Lineage` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Inferred Lineage Job` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Inferred Lineage Job` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Inferred Lineage Job` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Create Inferred Lineage Result` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Read Inferred Lineage Result` | ❌ | ✅ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |
| `Update Inferred Lineage Result` | ❌ | ❌ | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ |

### Enterprise Data Catalog permissions with custom roles

Securiti lets you select fine-grained permissions for each custom role you create in the Platform.

**Permission:** It is a parent permission that grants specific rights to perform certain actions within the system. For example, `Create Data Quality Finding`, `Update Data Quality Template`, and `Read Data Quality Expectation`.

**Explanation:** Describes why the permission is needed and the context in which it is used. For example, `Read Data Quality Template` and `Read Data Quality Template Type` permissions are required for `Create Data Quality Template`.

**Dependent permissions:** These are a set of permissions that are automatically applied in the same or different modules when a parent permission is selected.

This table lists the Enterprise Data Catalog permissions, explains the actions each permission allows, and specifies any dependent permissions that are automatically applied.

| Permission | Explanation | Dependent Permissions |
| --- | --- | --- |
| `Create Data Quality Checkpoint` | This permission lets you create data quality checkpoints. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Delete Data Quality Checkpoint` | This permission lets you delete data quality checkpoints. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Execute Data Quality Checkpoint` | This permission lets you execute data quality checkpoints. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Read Data Quality Checkpoint` | This permission lets you view data quality checkpoints. | - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Update Data Quality Checkpoint` | This permission lets you update data quality checkpoints. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Create Data Quality Expectation` | This permission lets you create data quality expectations. | - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Delete Data Quality Expectation` | This permission lets you delete data quality expectations. | - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Read Data Quality Expectation` | This permission lets you read data quality expectations. | - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Update Data Quality Expectation` | This permission lets you update data quality expectations. | - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Create Data Quality Finding` | This permission lets you create data quality findings. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Finding` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Delete Data Quality Finding` | This permission lets you delete data quality findings. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Finding` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Read Data Quality Finding` | This permission lets you read data quality findings. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Update Data Quality Finding` | This permission lets you update data quality findings. | - `Read Data Quality Checkpoint` - `Read Data Quality Expectation` - `Read Data Quality Finding` - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Create Data Quality Template` | This permission lets you create data quality templates. | - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Delete Data Quality Template` | This permission lets you delete data quality templates. | - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Read Data Quality Template` | This permission lets you read data quality templates. | - `Read Data Quality Template Type` |
| `Update Data Quality Template` | This permission lets you update data quality templates. | - `Read Data Quality Template` - `Read Data Quality Template Type` |
| `Create Data Quality Template Type` | This permission lets you create data quality template types. | - `Read Data Quality Template Type` |
| `Delete Data Quality Template Type` | This permission lets you delete data quality template types. | - `Read Data Quality Template Type` |
| `Read Data Quality Template Type` | This permission lets you read data quality template types. | No dependent permissions |
| `Update Data Quality Template Type` | This permission lets you update data quality template types. | - `Read Data Quality Template Type` |
| `Delete Assertions` | This permission lets you remove data quality assertions. | - `View Assertions` |
| `Manage Assertions` | This permission lets you have all available operations on assertions. This includes creating, updating, and deleting assertions. | No dependent permissions |
| `View Assertions` | This permission lets you view data quality assertions. | No dependent permissions |
| `Batch Soft Delete Charts` | This permission lets you bulk soft-delete multiple charts. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Create Chart` | This permission lets you create charts. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Delete Chart` | This permission lets you delete charts. Use with caution as this may affect associated dashboards. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Edit Chart Deprecation` | This permission lets you update chart deprecation status. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Edit Chart Embed Information` | This permission lets you edit embed information for charts, controlling how charts are embedded in other systems. | No dependent permissions |
| `Manage Charts` | This permission lets you perform all available operations on charts. This includes creating, editing, and deleting charts. | - `Manage Data Platforms` - `Manage Data Platform Instance Details` |
| `Remove Chart Custom Properties` | This permission lets you remove chart custom properties. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Remove Chart Structured Properties` | This permission lets you remove chart structured properties. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Custom Properties` | This permission lets you update chart custom properties. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Edit Chart Data Products` | This permission lets you update chart data products. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Links` | This permission lets you update chart links. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Description` | This permission lets you update chart descriptions. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Domains` | This permission lets you update chart domains. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Glossary Terms` | This permission lets you update chart glossary terms. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Owners` | This permission lets you update chart owners. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Structured Properties` | This permission lets you update chart structured properties. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Chart Tags` | This permission lets you update chart tags. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Chart` | This permission lets you view the charts page and browse available charts in the catalog. | - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Chart Audit` | This permission lets you view chart audit logs. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Chart Details` | This permission lets you view metadata and technical details of charts. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Create Container` | This permission lets you create containers. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Delete Container` | This permission lets you delete containers. | - `View Chart` - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Manage Containers` | This permission lets you perform all available operations on containers. This includes creating, editing, and deleting containers. | - `Manage Data Platforms` - `Manage Data Platform Instance Details` |
| `Remove Container Custom Properties` | This permission lets you remove container custom properties. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Remove Container Structured Properties` | This permission lets you remove container structured properties. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Custom Properties` | This permission lets you update container custom properties. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Edit Container Data Products` | This permission lets you update container data product associations. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Links` | This permission lets you update update or modify existing links associated with a container. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Description` | This permission lets you update container descriptions. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Domains` | This permission lets you update container domains. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Glossary Terms` | This permission lets you update container glossary terms. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Owners` | This permission lets you update container owners. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Structured Properties` | This permission lets you update container structured properties. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Container Tags` | This permission lets you update container tags. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Container` | This permission lets you view containers. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Container Audit` | This permission lets you view container audit logs. | - `View Container` - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Container Details` | This permission lets you view container details. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Create Group` | This permission lets you create groups. | - `View Users and Groups Details` - `View Ownership Types` |
| `Create Password Reset Token` | This permission lets you generate password reset tokens. | - `View Users and Groups Details` - `View Ownership Types` |
| `Edit Group Contact Information` | This permission lets you update group contact information. | - `View Users and Groups Details` - `View Ownership Types` |
| `Edit Group Members` | This permission lets you manage group members. | No dependent permissions |
| `Edit User Contact Information` | This permission lets you update user contact information. | - `View Users and Groups Details` - `View Ownership Types` |
| `Edit User Profile` | This permission lets you update user profiles. | - `View Users and Groups Details` - `View Ownership Types` |
| `Manager User Credentials` | This permission lets you manage user credentials. | - `View Users and Groups Details` - `View Ownership Types` |
| `Manage Users &amp; Groups` | This permission lets you manage users and groups. | No dependent permissions |
| `Remove Group` | This permission lets you delete groups. | - `View Users and Groups Details` - `View Ownership Types` |
| `Remove User` | This permission lets you delete users. | - `View Users and Groups Details` - `View Ownership Types` |
| `Update Group Description` | This permission lets you update group descriptions. | - `View Users and Groups Details` - `View Ownership Types` |
| `Update Group Members` | This permission lets you update group members. | - `View Users and Groups Details` - `View Ownership Types` |
| `Update Group Name` | This permission lets you update group names. | - `View Users and Groups Details` - `View Ownership Types` |
| `Update User Setting` | This permission lets you update user settings. | - `View Users and Groups Details` - `View Ownership Types` |
| `Update User Status` | This permission lets you update user status. | - `View Users and Groups Details` - `View Ownership Types` |
| `View Groups` | This permission lets you view groups. | No dependent permissions |
| `View Users And Groups Details` | This permission lets you view user and group details. | - `View Ownership Types` |
| `Create Glossary Custom Relationship Type` | This permission lets you define new custom relationship types for glossary entities. | - `View Glossary Custom Relationship Type Details` |
| `Delete Glossary Custom Relationship Type` | This permission lets you permanently remove custom relationship types. Note that this may impact existing links between glossary terms. | - `View Glossary Custom Relationship Type Details` |
| `Manage Glossary Custom Relationship Types` | This permission lets you perform all operations on glossary relationship types, including creation, modification, and deletion. | No dependent permissions |
| `Update Glossary Custom Relationship Type` | This permission lets you modify the properties or constraints of existing custom relationship types. | - `View Glossary Custom Relationship Type Details` |
| `View Glossary Custom Relationship Type Details` | This permission lets you view definitions and metadata of existing custom relationship types. | No dependent permissions |
| `Batch Soft Delete Dashboards` | This permission lets you bulk soft-delete multiple dashboards. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Create Dashboard` | This permission lets you create dashboards. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Delete Dashboard` | This permission lets you delete dashboards. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Edit Dashboard Deprecation` | This permission lets you update dashboard deprecation status. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Edit Dashboard Embed Information` | This permission lets you edit embed information for dashboards, controlling how dashboards are embedded in other systems. | No dependent permissions |
| `Manage Dashboards` | This permission lets perform all available operations on dashboards. This includes creating, editing, and deleting dashboards. | - `View Data Platform Details` - `View Data Platform Instance Details` |
| `Remove Dashboard Custom Properties` | This permission lets you remove dashboard custom properties. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Remove Dashboard Structured Properties` | This permission lets you remove dashboard structured properties. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Custom Properties` | This permission lets you update dashboard custom properties. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Edit Dashboard Data Products` | This permission lets you update dashboard data product. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Links` | This permission lets you update dashboard links. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Description` | This permission lets you update dashboard descriptions. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Domains` | This permission lets you update dashboard domains. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Glossary Terms` | This permission lets you update dashboard glossary terms. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Owners` | This permission lets you update dashboard owners. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Structured Properties` | This permission lets you update dashboard structured properties. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Update Dashboard Tags` | This permission lets you update dashboard tags. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Dashboard` | This permission lets you view dashboards. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Dashboard Audit` | This permission lets you view dashboard audit logs. | - `View Chart Details` - `View Users and Groups Details` - `View Dashboard` - `View Dashboard Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `View Dashboard Details` | This permission lets you view dashboard details. | - `View Chart Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tags Details` |
| `Batch Soft Delete DataFlows` | This permission lets you bulk soft-delete data flows. | No dependent permissions |
| `Create Dataflow` | This permission lets you create data flows. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete Dataflow` | This permission lets you delete data flows. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataflow Deprecation` | This permission lets you update data flow deprecation status. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage Dataflows` | This permission lets you manage data flows. | - `Manage Data Platforms` - `Manage Data Platform Instance Details` |
| `Remove Dataflow Custom Properties` | This permission lets you remove data flow custom properties. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove Dataflow Structured Properties` | This permission lets you remove data flow structured properties. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataflow Custom Properties` | This permission lets you update data flow custom properties. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataflow Data Products` | This permission lets you update data flow data products. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataFlow Links` | This permission lets you update data flow links. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataFlow Description` | This permission lets you update data flow descriptions. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataFlow Domains` | This permission lets you update data flow domains. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataFlow Glossary Terms` | This permission lets you update data flow glossary terms. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataFlow Owners` | This permission lets you update data flow owners. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataFlow Structured Properties` | This permission lets you update data flow structured properties. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataFlow Tags` | This permission lets you update data flow tags. | - `View Users and Groups Details` - `View Dataflow` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View DataFlow` | This permission lets you view data flows and browse available dataflows in the catalog. | - `View Users and Groups Details` - `View Dataflow Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View DataFlow Audit` | This permission lets you view data flow audit logs. | No dependent permissions |
| `View DataFlow Details` | This permission lets you view data flow details. | - `View Users and Groups Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create Policy` | This permission lets you create policies. | `View Policy` |
| `Delete Policy` | This permission lets you delete policies. | `View Policy` |
| `Manage Policies` | This permission lets you manage policies. | No dependent permissions |
| `Update Policy` | This permission lets you update policies. | `View Policy` |
| `View Policy` | This permission lets you view policies. | No dependent permissions |
| `Create Secret` | This permission lets you create secrets. | `View Secrets Metadata` |
| `Delete Secret` | This permission lets you delete secrets. | `View Secrets Metadata` |
| `Manage Secrets` | This permission lets you manage secrets. | No dependent permissions |
| `View Secrets Metadata` | This permission lets you view secrets metadata. | No dependent permissions |
| `Create View` | This permission lets you create views. | No dependent permissions |
| `Delete View` | This permission lets you delete views. | No dependent permissions |
| `Manage Global Views` | This permission lets you manage global views. | No dependent permissions |
| `Update Personal Views` | This permission lets you update personal views. | No dependent permissions |
| `Update Global Views Settings` | This permission lets you update global view settings. | No dependent permissions |
| `Update View` | This permission lets you update views. | No dependent permissions |
| `View Global Views` | This permission lets you view global views. | No dependent permissions |
| `Batch Soft Delete DataJobs` | This permission lets you bulk soft-delete data jobs. | No dependent permissions |
| `Create DataJob` | This permission lets you create data jobs. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete DataJob` | This permission lets you delete views. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit DataJob Deprecation` | This permission lets you update data job deprecation status. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage DataJobs` | This permission lets you manage data jobs. | - `Manage Data Platforms` - `Manage Data Platform Instances` |
| `Remove DataJob Custom Properties` | This permission lets you remove data job custom properties. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove DataJob Structured Properties` | This permission lets you remove data job structured properties. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Custom Properties` | This permission lets you update data job custom properties. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit DataJob Data Products` | This permission lets you update data job data products. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Links` | This permission lets you update data job links. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Description` | This permission lets you update data job description. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Domains` | This permission lets you update data job domains. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Glossary Terms` | This permission lets you update data job glossary terms. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Owners` | This permission lets you update data job owners. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Structured Properties` | This permission lets you update data job structured properties. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update DataJob Tags` | This permission lets you update data job tags. | - `View Users and Groups Details` - `View DataJob` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View DataJob` | This permission lets you view data jobs. | - `View Users and Groups Details` - `View DataJob Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View DataJob Audit` | This permission lets you view data job audit logs. | No dependent permissions |
| `View DataJob Details` | This permission lets you view data job audit details. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage Data Platforms` | This permission lets you create, edit, and manage data platforms in the catalog. | No dependent permissions |
| `Manage Data Platform Instances` | This permission lets you manage data platform instances. This includes create, edit, and manage instances of data platforms in the catalog. | No dependent permissions |
| `View Data Platform Details` | This permission lets you view data platform details. | No dependent permissions |
| `View Data Platform Instance Details` | This permission lets you view data platform instance details. | - `View Users and Groups Details` - `View Data Platform Details` - `View Ownership Types` |
| `Edit Data Process Instance Lineage` | This permission lets you update data process instance lineage. | No dependent permissions |
| `Manage Data Process Instance Groups` | This permission lets you manage data process instance groups. | No dependent permissions |
| `Batch Soft Delete Data Products` | This permission lets you bulk soft-delete data products. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Import Data Product` | This permission lets you import data products. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create Data Product` | This permission lets you create data products. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete Data Product` | This permission lets you delete data products. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Export Data Product Assets` | This permission lets you export data product assets. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage Data Products` | This permission lets you manage data products. | No dependent permissions |
| `Remove Data Product Custom Property` | This permission lets you remove data product custom properties. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove Data Product Structured Property` | This permission lets you remove data product structured properties. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product` | This permission lets you update data products. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Custom Property` | This permission lets you update data product custom properties. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Description` | This permission lets you update data product description. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Domains` | This permission lets you update data product domains. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Glossary Terms` | This permission lets you update data product glossary terms. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Governance Status` | This permission lets you update data product governance status. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Link` | This permission lets you update data product links. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Name` | This permission lets you update data product names. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Owner` | This permission lets you update data product owners. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Structured Property` | This permission lets you update data product structured properties. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Data Product Tags` | This permission lets you update data product tags. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Data Product Audit` | This permission lets you view data product audit logs. | - `View Users and Groups Details` - `View Data Product Details` - `View Data Products` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Data Product Details` | This permission lets you view data product audit details. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Data Products` | This permission lets you view data products. | - `View Users and Groups Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Data Product Assets` | This permission lets you view data product assets. | No dependent permissions |
| `Batch Add Schema Metadata` | This permission lets you add metadata to multiple schemas in bulk. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Batch Soft Delete Datasets` | This permission lets you remove multiple datasets. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Batch Soft Delete Queries` | This permission lets you remove multiple queries. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Queries` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Import Dataset` | This permission lets you import datasets. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create Dataset` | This permission lets you create datasets. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create Dataset Query` | This permission lets you create dataset queries. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Queries` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete Dataset` | This permission lets you delete datasets. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete Dataset Query` | This permission lets you delete dataset queries. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Queries` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Column Descriptions` | This permission lets you update dataset column descriptions. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Column Domains` | This permission lets you update dataset column domains. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Column Glossary Terms` | This permission lets you update dataset column glossary terms. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Column Governance Flag` | This permission lets you update the governance flag for dataset columns. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Column Tags` | This permission lets you update dataset column tags. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Deprecation` | This permission lets you update the deprecation status of datasets. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Queries` | This permission lets you update dataset queries. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Embed Information` | This permission lets you update dataset embed information. | No dependent permissions |
| `Edit Dataset Entity Operations` | This permission lets you update dataset entity operations. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Read-Only Status` | This permission lets you update dataset read-only status. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Data Product Read-Only Status` | This permission lets you update data product read-only status. | - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Data Products` - `View Data Product Details` - `View Glossary Custom Relationship Type Details` |
| `Edit Glossary Node Read-Only Status` | This permission lets you update glossary node read-only status. | - `View Glossary Custom Relationship Type Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Edit Glossary Term Read-Only Status` | This permission lets you update glossary term read-only status. | - `View Glossary Custom Relationship Type Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Export Dataset` | This permissions lets you export datasets. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage Datasets` | This permissions lets you manage datasets. | - `View Container Details` - `View Users and Groups Details` - `Manage Data Platform` - `Manage Data Platform Instances` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage Dataset Query` | This permissions lets you manage dataset queries. | No dependent permissions |
| `Remove Dataset Custom Properties` | This permissions lets you remove dataset custom properties. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove Dataset Structured Properties` | This permissions lets you remove dataset structured properties. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Custom Properties` | This permissions lets you update dataset custom properties. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Edit Dataset Data Products` | This permissions lets you update dataset data products. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Links` | This permissions lets you update dataset links. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Description` | This permissions lets you update dataset descriptions. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Domains` | This permissions lets you update dataset domains. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Glossary Terms` | This permissions lets you update dataset glossary terms. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Governance Flag` | This permissions lets you update dataset governance flag. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Governance Status` | This permissions lets you update dataset governance status. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Owners` | This permissions lets you update dataset owners. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Query` | This permissions lets you update dataset queries. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Queries` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Structured Properties` | This permissions lets you update dataset structured properties. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Dataset Tags` | This permissions lets you update dataset tags. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Dataset` | This permissions lets you view datasets. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Dataset Audit` | This permissions lets you view dataset audit logs. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Dataset Details` | This permissions lets you view dataset details. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Dataset Profile` | This permissions lets you view dataset profiles. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Dataset Usage` | This permissions lets you view dataset usage. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Queries` | This permissions lets you view queries. | - `View Container Details` - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Dataset` - `View Dataset Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Batch Soft Delete Domains` | This permissions lets you remove multiple domains. | - `View Users and Groups Details` - `View Domains` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Create Domain` | This permissions lets you create domains. | - `View Users and Groups Details` - `View Domains` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Delete Domain` | This permissions lets you delete domains. | No dependent permissions |
| `Manage Domains` | This permissions lets you manage domains. | No dependent permissions |
| `Remove Domain Custom Property` | This permissions lets you remove domain custom properties. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Domain Structured Property` | This permissions lets you remove domain structured properties. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Domain Custom Property` | This permissions lets you update domain custom properties. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Domain Description` | This permissions lets you update domain description. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Domain Link` | This permissions lets you update domain links. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Domain Name` | This permissions lets you update domain names. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Domain Owner` | This permissions lets you update domain owners. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Move Domain` | This permissions lets you move domains. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Domain Structured Property` | This permissions lets you update domain structured properties. | - `View Users and Groups Details` - `View Domain` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Domain` | This permissions lets you view domains. | - `View Users and Groups Details` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Domain Details` | This permissions lets you view domain details. | - `View Users and Groups Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Add Related Nodes to Glossary Nodes` | This permissions lets you add related nodes to glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Add Related Terms to Glossary Nodes` | This permissions lets you add related terms to glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Batch Soft Delete Glossary Nodes` | This permissions lets you soft-delete multiple glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Create Glossary Node` | This permissions lets you create glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Delete Glossary Node` | This permissions lets you delete glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Manage Glossary Nodes` | This permissions lets you manage glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Glossary Node Custom Property` | This permissions lets you remove glossary node custom properties. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Related Nodes from Glossary Node` | This permissions lets you remove related nodes from glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Related Terms from Glossary Node` | This permissions lets you remove related terms from glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Glossary Node Structured Property` | This permissions lets you remove glossary node structured property. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Custom Property` | This permissions lets you update glossary node custom properties. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Description` | This permissions lets you update glossary node description. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Domain` | This permissions lets you update glossary node domain. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Governance` | This permissions lets you update glossary node governance. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Governance Flag` | This permissions lets you update glossary node governance flag. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Name` | This permissions lets you update glossary node name. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Owner` | This permissions lets you update glossary node owner. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Move Glossary Node` | This permissions lets you move glossary node. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Structured Property` | This permissions lets you update glossary node structured property. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Node Structured Subtype` | This permissions lets you update glossary node structured subtype. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Glossary Nodes` | This permissions lets you view glossary nodes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Glossary Node Audit` | This permissions lets you view glossary node audit logs. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Glossary Node Details` | This permissions lets you view glossary node details. | - `View Users and Groups Details` - `View Domain Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Add Related Nodes to Glossary Term` | This permissions lets you add related nodes to glossary terms. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Add Related Terms to Glossary Term` | This permissions lets you add related terms to glossary terms. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Batch Soft Delete Glossary Terms` | This permissions lets you delete multiple glossary terms. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Bulk Glossary Export` | This permissions lets you export multiple glossary terms at once for backup, migration, or external use, independent of specific term URNs. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Bulk Glossary Import` | This permissions lets you import multiple glossary terms at once from external sources, enabling efficient bulk creation and updates of business vocabulary. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Clone Glossary Term` | This permissions lets you create copies of existing glossary terms, useful for creating similar terms with slight variations or for testing purposes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Create Glossary Term` | This permissions lets you create new glossary terms to define business vocabulary and standardize data concepts across the organization. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Delete Glossary Term` | This permissions lets you permanently delete glossary terms. Use with caution as this may affect data assets tagged with this term. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Manage Glossary Terms` | This permission lets you have all available operations on glossary terms. This includes creating, viewing, updating, moving, cloning, and deleting glossary terms. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Mark Glossary Term Deprecated` | This permission lets you mark glossary terms as deprecated, indicating that they should no longer be used while maintaining historical reference. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Glossary Term Custom Property` | This permission lets you remove custom properties from glossary terms, cleaning up custom metadata when no longer needed. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Related Nodes From Glossary Term` | This permission lets you remove associations between glossary terms and nodes, breaking existing organizational relationships. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Related Terms From Glossary Term` | This permission lets you remove relationships between glossary terms, breaking existing cross-references when no longer relevant. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Remove Glossary Term Structured Property` | This permission lets you remove structured properties from glossary terms, cleaning up metadata when no longer needed. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Custom Property` | This permission lets you add or update custom properties on glossary terms for flexible, organization-specific metadata management. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Description` | This permission lets you update the description of glossary terms to provide clearer definitions and better context for business concepts. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Domain` | This permission lets you assign or update the domain association of glossary terms for better organization across business domains. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Governance` | This permission lets you manage governance settings for glossary terms, including both governance flags and governance status for compliance and data governance purposes. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Governance Flag` | This permission lets you manage governance Flag settings for glossary terms, including both governance flags and governance status for compliance and data governance purposes. | No dependent permissions |
| `Update Glossary Term Link` | This permission lets you add or update external links associated with glossary terms for additional documentation or resources. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Name` | This permission lets you update the name of glossary terms for better clarity and consistency in business vocabulary. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Owner` | This permission lets you update or change the ownership of glossary terms for better accountability and governance of business vocabulary. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Move Glossary Term` | This permission lets you move glossary terms within the hierarchy by changing their parent node, enabling reorganization of business vocabulary structure. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Structured Property` | This permission lets you add or update structured properties on glossary terms for enhanced metadata management and standardization of business vocabulary. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Update Glossary Term Subtype` | This permission lets you update the subtype classification of glossary terms for better categorization and organization of business vocabulary. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Glossary Terms` | This permission lets you view the glossary terms page in the UI and browse the business glossary for standardized terminology. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Glossary Term Audit` | This permission lets you view change log of glossary term. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Nodes` - `View Glossary Node Details` - `View Glossary Terms` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` |
| `View Glossary Term Details` | This permission lets you view detailed information about specific glossary terms, including their definitions, relationships, and usage across data assets. | - `View Users and Groups Details` - `View Domain Details` - `View Glossary Node Details` - `View Ownership Types` - `View Structured Properties Details` |
| `Cancel Ingestion` | This permission lets you stop a running ingestion execution. | - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Ingestion` - `View Ingestion Details` |
| `Run Ingestion` | This permission lets you manually trigger an ingestion run. | - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Ingestion` - `View Ingestion Details` |
| `Create Ingestion Source` | This permission lets you create new ingestion source configurations. | - `View Secrets Metadata` - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Ingestion` - `View Ingestion Details` - `View Appliance List` - `View Data Sources` - `View Supported Connectors` |
| `Delete Ingestion Source` | This permission lets you remove ingestion source configurations. | - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Ingestion` - `View Ingestion Details` |
| `Manage Metadata Ingestion` | This permission lets you have all available operations on metadata ingestion. This includes creating, removing, and updating metadata ingestion sources. | - `View Secrets Metadata` - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Appliance List` - `View Data Sources` - `View Supported Connectors` |
| `Rollback Ingestion` | This permission lets you rollback or undo the effects of a metadata ingestion run, removing ingested metadata from the catalog. | - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Ingestion` - `View Ingestion Details` |
| `Update Ingestion Source` | This permission lets you update ingestion source configurations. | - `View Secrets Metadata` - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Ingestion` - `View Ingestion Details` - `View Appliance List` - `View Data Sources` - `View Supported Connectors` |
| `View Ingestion` | This permission lets you view ingestion page. | - `Manage Data Platforms` - `Manage Data Platform Instances` - `View Ingestion Details` |
| `View Ingestion Details` | This permission lets you view ingestion sources and execution history. | No dependent permissions |
| `Edit Chart Lineage` | This permission lets you add and remove lineage edges for charts, tracking data sources used in visualizations. | No dependent permissions |
| `Edit Dashboard Lineage` | This permission lets you add and remove lineage edges for dashboards, showing which datasets feed into visualizations. | No dependent permissions |
| `Edit DataFlow Lineage` | This permission lets you add and remove lineage edges for data flows (pipelines), tracking data movement and transformations. | No dependent permissions |
| `Edit DataJob Lineage` | This permission lets you add and remove lineage edges for data jobs, documenting data transformation processes. | No dependent permissions |
| `Edit Dataset Lineage` | This permission lets you add and remove lineage edges (upstream/downstream connections) for datasets. | No dependent permissions |
| `Edit Lineage` | This permission lets you add and remove lineage edges for entities in the catalog. | No dependent permissions |
| `Edit ML Feature Lineage` | This permission lets you add and remove lineage edges for machine learning features. | No dependent permissions |
| `Edit ML Feature Table Lineage` | This permission lets you add and remove lineage edges for machine learning feature tables. | No dependent permissions |
| `Edit ML Model Lineage` | This permission lets you add and remove lineage edges for machine learning models, tracking training data and model dependencies. | No dependent permissions |
| `Edit ML Model Group Lineage` | This permission lets you add and remove lineage edges for machine learning model groups. | No dependent permissions |
| `Edit ML Primary Key Lineage` | This permission lets you add and remove lineage edges for machine learning primary keys. | No dependent permissions |
| `Create ML Feature` | This permission lets you create ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete ML Feature` | This permission lets you delete ML features. Use with caution as this may affect associated ML workflows. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage ML Feature Key` | This permission lets you manage ML features. | - `Manage Data Platforms` - `Manage Data Platform Instance` |
| `Remove ML Feature Custom Properties` | This permission lets you remove custom properties from ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove ML Feature Structured Properties` | This permission lets you remove structured properties from ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Custom Properties` | This permission lets you update custom properties for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Data Products` | This permission lets you add or remove data products for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Documentation Links` | This permission lets you update documentation links for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Documentation` | This permission lets you update documentation for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Domains` | This permission lets you update domain associations for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Glossary Terms` | This permission lets you update glossary terms for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Owners` | This permission lets you update ownership information for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Structured Properties` | This permission lets you update structured properties for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Tags` | This permission lets you update tags for ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View ML Feature` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Feature Details` | This permission lets you view metadata and technical details of ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Feature` | This permission lets you view ML features. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create ML Feature Table` | This permission lets you create ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature TableView Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete ML Feature Table` | This permission lets you delete ML feature tables. Use with caution as this may affect associated ML workflows. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage ML Feature Table` | This permission lets you manage ML Feature tables. | - `Manage Data Platforms` - `Manage Data Platform Instances` |
| `Remove ML Feature Table Custom Properties` | This permission lets you remove custom properties from ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove ML Feature Table Structured Properties` | This permission lets you remove structured properties from ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Custom Properties` | This permission lets you update custom properties for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Data Products` | This permission lets you add or remove data products for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Documentation Links` | This permission lets you update documentation links for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Documentation` | This permission lets you update documentation for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Domains` | This permission lets you update domain associations for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Glossary Terms` | This permission lets you update glossary terms for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Owners` | This permission lets you update ownership information for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Structured Properties` | This permission lets you update structured properties for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Feature Table Tags` | This permission lets you update tags for ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Feature Table Details` | This permission lets you view metadata and technical details of ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Feature Table` | This permission lets you view ML feature tables. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create ML Model` | This permission lets you create ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete ML Model` | This permission lets you delete ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Feature Table Details` - `View ML Feature Table` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage ML Model` | This permission lets you manage ML models. | - `Manage Data Platforms` - `Manage Data Platform Instances` |
| `Remove ML Model Custom Properties` | This permission lets you remove custom properties from ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove ML Model Structured Properties` | This permission lets you remove structured properties from ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Custom Properties` | This permission lets you update custom properties for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Data Products` | This permission lets you add or remove data products for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Documentation Links` | This permission lets you update documentation links for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Documentation` | This permission lets you update documentation for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Domains` | This permission lets you update domain associations for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Glossary Terms` | This permission lets you update glossary terms for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Owners` | This permission lets you update ownership information for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Structured Properties` | This permission lets you update structured properties for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Tags` | This permission lets you update tags for ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Model Audit` | This permission lets you view audit trails for ML models. | No dependent permissions |
| `View ML Model Details` | This permission lets you view metadata and technical details of ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Model` | This permission lets you view ML models. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create ML Model Group` | This permission lets you create a new ML model group. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete ML Model Group` | This permission lets you delete a ML model group. Use with caution as this may affect associated ML workflows. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage ML Model Group` | This permission lets you manage a ML Model Group. | - `Manage Data Platforms` - `Manage Data Platform Instances` |
| `Remove ML Model Group Custom Properties` | This permission lets you remove custom properties from ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove ML Model Group Structured Properties` | This permission lets you remove structured properties from ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Custom Properties` | This permission lets you update custom properties for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Data Products` | This permission lets you add or remove data products for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Documentation Links` | This permission lets you update documentation links for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Documentation` | This permission lets you update documentation for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Domains` | This permission lets you update domain associations for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Glossary Terms` | This permission lets you update glossary terms for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Owners` | This permission lets you update ownership information for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Structured Properties` | This permission lets you update structured properties for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Model Group Tags` | This permission lets you update tags for ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View ML Model Group` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Model Group Details` | This permission lets you view metadata and technical details of ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Model Group` | This permission lets you view ML model groups. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Model Group Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create ML Primary Key` | This permission lets you create a new ML primary key. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Delete ML Primary Key` | This permission lets you delete a ML primary key. Use with caution as this may affect associated ML workflows. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage ML Primary Key` | This permission lets you manage a ML primary key. | - `Manage Data Platforms` - `Manage Data Platform Instances` |
| `Remove ML Primary Key Custom Properties` | This permission lets you remove custom properties from ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Remove ML Primary Key Structured Properties` | This permission lets you remove structured properties from ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Custom Properties` | This permission lets you update custom properties for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Data Products` | This permission lets you add or remove data products for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Documentation Links` | This permission lets you update documentation links for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Documentation` | This permission lets you update documentation for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Domains` | This permission lets you update domain associations for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Glossary Terms` | This permission lets you update glossary terms for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Owners` | This permission lets you update ownership information for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Structured Properties` | This permission lets you update structured properties for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update ML Primary Key Tags` | This permission lets you update tags for ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View ML Primary Key` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Primary Key Details` | This permission lets you view metadata and technical details of ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View ML Primary Key` | This permission lets you view ML primary keys. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View ML Primary Key Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Manage Notebook` | This permission lets you perform available operations on notebooks. This includes creating, updating, and deleting notebooks. | - `Manage Data Platforms` - `Manage Data Platform Instances` |
| `Edit Notebook Data Products` | This permission lets you add or remove data products for notebooks. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Notebook` - `View Notebook Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Notebook Links` | This permission lets you update or modify existing links associated with a notebook. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Notebook` - `View Notebook Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Notebook Description` | This permission lets you edit the description (documentation) of a notebook. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Notebook` - `View Notebook Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Notebook Owners` | This permission lets you update owners of a notebook. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Notebook` - `View Notebook Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Update Notebook Tags` | This permission lets you manage (add or remove) tags for a notebook. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Notebook` - `View Notebook Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Notebook` | This permission lets you view the notebooks page in the UI and browse available notebooks in the catalog. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Notebook Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `View Notebook Details` | This permission lets you view details of notebooks. | - `View Users and Groups Details` - `View Data Platform Details` - `View Data Platform Instance Details` - `View Data Product Details` - `View Domain Details` - `View Glossary Node Details` - `View Glossary Term Details` - `View Ownership Types` - `View Structured Properties Details` - `View Tag Details` |
| `Create Ownership Type` | This permission lets you create new ownership types in DataHub. | `View Ownership Types` |
| `Delete Ownership Type` | This permission lets you delete ownership types from DataHub. | `View Ownership Types` |
| `Manage Global Ownership Types` | This permission lets you manage global ownership types across the organization. | No dependent permissions |
| `Update Ownership Type` | This permission lets you update existing ownership types in DataHub. | `View Ownership Types` |
| `View Ownership Types` | This permission lets you view available ownership types (e.g., Technical Owner, Business Owner) in the catalog. | No dependent permissions |
| `Create Global Announcements` | This permission lets you create new global announcements and posts that appear on the home page. | No dependent permissions |
| `Delete Global Announcements` | This permission lets you delete existing global announcements and posts from the home page. | No dependent permissions |
| `Manage Home Page Posts` | This permission lets you create and delete home page posts and announcements for all users to see. | No dependent permissions |
| `View Posts` | This permission lets you view announcements and posts on the home page. | No dependent permissions |
| `Accept Role` | This permission lets you accept roles assigned to user. | `View Roles` |
| `Create Invite Token` | This permission lets you create invitation tokens for role assignments. | `View Invite Token` |
| `Manage Roles` | This permission lets you perform all available operations on roles. This includes creating, updating, and deleting roles in DataHub. | No dependent permissions |
| `View Invite Token` | This permission lets you view invitation tokens. | No dependent permissions |
| `View Roles` | This permission lets you view available RBAC roles and their assigned privileges. | No dependent permissions |
| `Batch Soft Delete Structured Properties` | This permission lets you bulk soft-delete structured properties. | No dependent permissions |
| `Create Structured Properties` | This permission lets you create new structured property definitions. | - `View Structured Properties` - `View Structured Properties Details` |
| `Delete Structured Properties` | This permission lets you delete structured property definitions. | - `View Structured Properties` - `View Structured Properties Details` |
| `Manage Structured Properties` | This permission lets you perfrom available operations on structured properties. This includes creating, updating, and deleting structured property definitions. | No dependent permissions |
| `Update Structured Properties` | This permission lets you update existing structured property definitions. | - `View Structured Properties` - `View Structured Properties Details` |
| `View Structured Properties` | This permission lets you view the structured properties page in the UI and browse available structured properties in the catalog. | `View Structured Properties Details` |
| `View Structured Properties Details` | This permission lets you view custom structured properties and their definitions. | No dependent permissions |
| `Generate Personal Tokens` | This permission lets you generate personal access tokens. | No dependent permissions |
| `Get Analytics` | This permission lets you read access to raw analytics data. | No dependent permissions |
| `Get Entity Counts` | This permission lets you retrieve count statistics for various entities in the system. | No dependent permissions |
| `Get System Timeline` | This permission lets you retrieve timeline data for system events and changes. | No dependent permissions |
| `Get Time Series Aspects` | This permission lets you retrieve time series aspect data from the system. | No dependent permissions |
| `Manage Access Tokens` | This permission lets you create, view, and manage system access tokens for API authentication. | No dependent permissions |
| `Manage Retention Policies` | This permission lets you manage retention policies. | No dependent permissions |
| `Produce Platform Events` | This permission lets you generate and publish platform-level events for system integration. | No dependent permissions |
| `View Analytics` | This permission lets you view analytics. | `Get Analytics` |
| `View Appliance List` | This permission lets you view appliance list. | No dependent permissions |
| `View Data Sources` | This permission lets you view data sources. | No dependent permissions |
| `View Supported Connectors` | This permission lets you view supported connectors. | No dependent permissions |
| `Create Tag` | This permission lets you create new tags for categorizing and organizing data assets. | - `View Users And Groups Details` - `View Ownership Types` - `View Tag Details` |
| `Delete Tag` | This permission lets you permanently delete tags from the catalog. Use with caution as this may affect associated data assets. | - `View Users And Groups Details` - `View Ownership Types` - `View Tag Details` |
| `Manage Tags` | This permission lets you perform all available operations on tags. This includes creating, viewing, updating, and deleting tags. | No dependent permissions |
| `Update Tag` | This permission lets you update tags for organization. | No dependent permissions |
| `Update Tag Color` | This permission lets you add or update the color of tags for better visual organization and identification. | - `View Users And Groups Details` - `View Ownership Types` - `View Tag Details` |
| `Update Tag Description` | This permission lets you update the description of existing tags to provide better context and documentation. | - `View Users And Groups Details` - `View Ownership Types` - `View Tag Details` |
| `Update Tag Owner` | This permission lets you update or change the ownership of tags for better accountability and governance. | - `View Users And Groups Details` - `View Ownership Types` - `View Tag Details` |
| `View Tag` | This permission lets you view the tags page in the UI and browse available tags in the catalog. | - `View Users And Groups Details` - `View Ownership Types` - `View Tag Details` |
| `View Tag Audit` | This permission lets you view audit trails and change history for tags. | - `View Users And Groups Details` - `View Ownership Types` - `View Tag Details` |
| `View Tag Details` | This permission lets you view detailed information about specific tags, including their properties and associations. | - `View Users And Groups Details` - `View Ownership Types` |
| `Create Test` | This permission lets you create test entities. | - `View Test Details` - `View Tests` |
| `Delete Test` | This permission lets you delete existing test entities. | - `View Test Details` - `View Tests` |
| `Manage Tests` | This permission lets you have all available operations on tests. This includes creating and removing asset tests. | No dependent permissions |
| `Update Test` | This permission lets you update tests. | - `View Test Details` - `View Tests` |
| `View Test Details` | This permission lets you view test entity details. | No dependent permissions |
| `View Tests` | This permission lets you view tests. | No dependent permissions |
| `Create Inferred Lineage` | This permission lets you create inferred lineage. | - `Read Inferred Lineage` |
| `Execute Inferred Lineage` | This permission lets you execute inferred lineage. | - `Read Inferred Lineage` |
| `Read Inferred Lineage` | This permission lets you read inferred lineage. | No dependent permissions |
| `Update Inferred Lineage` | This permission lets you update inferred lineage. | - `Read Inferred Lineage` |
| `Create Inferred Lineage Job` | This permission lets you create inferred lineage job. | - `Read Inferred Lineage` - `Read Inferred Lineage Job` |
| `Read Inferred Lineage Job` | This permission lets you read inferred lineage job. | - `Read Inferred Lineage` |
| `Update Inferred Lineage Job` | This permission lets you update inferred lineage job. | - `Read Inferred Lineage` - `Read Inferred Lineage Job` |
| `Create Inferred Lineage Result` | This permission lets you update inferred lineage result. | - `Read Inferred Lineage` - `Read Inferred Lineage Job` - `Read inferred Lineage Result` |
| `Read Inferred Lineage Result` | This permission lets you read inferred lineage result. | - `Read Inferred Lineage` - `Read Inferred Lineage Job` |
| `Update Inferred Lineage Result` | This permission lets you update inferred lineage result. | - `Read Inferred Lineage` - `Read Inferred Lineage Job` - `Read inferred Lineage Result` |
