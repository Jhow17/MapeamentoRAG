---
title: "Data System Migration across Organizations in Securiti"
slug: "data-system-migration-across-organizations-in-securiti"
updated: 2026-08-03T05:51:37Z
published: 2026-08-03T05:51:37Z
canonical: "helpcenter.securiti.ai/data-system-migration-across-organizations-in-securiti"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Data System Migration across Organizations in Securiti

In multi-organization Securiti tenants, you might need to move data systems such as Data System Instance, Connector, and associated policies from one organization to another. This guide outlines the process for enabling secure and efficient migration while maintaining data integrity, access controls, and user clarity.

This migration capability lets you:

- Limit access and visibility of data systems within organizational boundaries
- Migrate data systems across organizations under the same tenant without disrupting connected systems.

### Relationship between organization and data system

Securiti connects to each Data system by provisioning a Data System Instance, which includes configuring the Hosting environment, such as Private Storage, SaaS, or IaaS. Under each Data system Instance, you can then authenticate and activate a data system connector to establish a Connection between your Data system and Securiti.

To streamline migration and organization management, Securiti uses a parent-child model with the following characteristics:

- Each Data system Instance belongs to a specific organization
- Dependent elements, such as **connectors** or **scan settings**, do not carry individual organization tags.

This relation design reduces complexity during migration and ensures a consistent structure.

### Validation checks

You must check whether the Data system is eligible for migration.

Validation checks include:

- No attached discovery scans
- No attached scan policies that block migration
- No active workflows connected to the system
- No current Data system owner available in the destination organization

### Handling module components

Securiti evaluates and manages linked module components individually during migration:

| Linked Component | Migration action |
| --- | --- |
| Data Subject Requests (DSR) | - Complete the running DSR requests, as in-progress DSR requests are removed during migration. - No action is required for completed DSR requests, as they remain unchanged and stay in the existing organization. |
| Breach Incidents | > [!NOTE] > Note > > Securiti doesn’t let you migrate the Data system if there is a Breach Incident associated with it, is in an open state. - Check for open incidents associated with the Data system Instance, and do one of the following actions to initiate migration: - Remove the data asset from the Incident. - Or change the Incident organization and attach a new data asset in the destination organization. - No action needed for completed incidents |
| Workflows | Check if there is any active Workflow attached to the Data system Instance. Migration is blocked if the Data system Instance is part of an active Workflow. |
| Data mapping assets | No action required as Securiti migrates all associated data mapping assets with the Data system Instance to the target organization. |
| Discovery Scans | Check if discovery scans are attached to a Data system Instance: - Securiti doesn’t let you migrate the Data system Instance if Discovery scan(s) are attached. - You must delete the discovery scans to allow the Data system migration. |
| Data Labeling policies | Check for Data Labeling policies associated with the Data system Instance: - To migrate the Data system, you must delete the associated policies using the deactivate and purge connectors. > [!NOTE] > Note > > Data system Migration is not possible while Data Labeling policies are associated with the Data system. |
| Data Masking policies | Check for Data Masking policies associated with the Data system Instance: - To migrate the Data system, you must delete the associated Data Masking policies using the deactivate and purge connectors. > [!NOTE] > Note > > Data system Migration is not allowed while Data Masking policies are associated with the Data system. |
| Security Posture policies | Securiti allows the Data system migration if Security Posture policies are associated with the Data system Instance. Check for open Securiti Posture Findings associated with the Data system Instance: - Securiti closes the associated Security Posture findings and doesn’t show in the destination organization after migration. |
| Exact Data Match (EDM) | Check if the Exact Data Match profile is attached to the Data system Instance. In this case, migration is blocked. If no Exact Data Match Profile is attached to the Data system Instance, Securiti moves EDM templates to the target organization. |
| Custom Document Types | No action is required as Custom Document Type is an independent option. You can migrate a Data system Instance with custom document types. |

### Procedure

If validation checks are successful, you can start the Data system migration process by following the steps below:

1. Open the Data system Instance that you want to migrate to the new organization.
2. On Overview screen, click dropdown > Migrate Data system.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-5AYYN7OL.png)

> [!NOTE]
> **Note**
> 
> **Migrate Data system** option only appears if you have an activated Connector within your Data system Instance.
3. On the **Migrating Data system** pop-up, apply the following settings:
  1. Select the **Target Organization**.

> [!WARNING]
> Caution
> 
> In case of Self-hosted connectors, you might see an error message in case of the following conditions:
> 
> - The Data system Instance is in the Authentication, Learning, or scanning stage.
> - The destination organization has the Data system Instance with the same Activation Credentials.
> - The Discovery scan is attached to the Data system Instance.
> - The Security Posture scan is scheduled or collecting state for the Data system Instance.
  2. Select the **Content Scan Policy** set in the target organization.
  3. Click **Start Migration**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GEBIWP2Q.png)
4. Once the migration is complete, it notifies with a success notification.

### Ownership and access control

Securiti handles the ownership and access controls during and after the migration is completed. Ownership handover prompts ensure clear user responsibilities

The table below shows the process of ownership handling during the Data system migration:

| Owner role | Description |
| --- | --- |
| Primary owner | Securiti preserves the Primary Owner if it exists in the target organization. |
| New owner | You must assign a new owner if the Primary Owner does not exist in the target organization. |
| Co-Owner | Securiti removes Co-owners during migration to maintain access control integrity. |

### Naming and uniqueness handling

Securiti handles naming duplication and uniqueness to ensure a clean and predictable post-migration setup. To avoid naming conflicts in the target organization:

- The system checks for **duplicate names**, such as the Connector type and the Data system name.
- Conflicts are resolved by appending temporary suffixes or stopping the migration, if necessary.

### Authorization and Security Controls

To enhance data security and maintain organizational boundaries, Securiti implements the following measures:

| Security Measure | Description |
| --- | --- |
| Additional authorization layers | Users only access systems within their own organization. |
| Reporting and analytics | Reporting views and analytics work within organizational boundaries. |
| Secure shared systems | Shared systems, such as Connector pods, remain functional without exposing cross-organization data. |

A collection of organized data or repositories and their corresponding management software, which could be IaaS, SaaS, or SQL. Data systems are configured in Securiti so that it can help you protect sensitive data and also locate personal data for data subjects who submit DSR requests. Data systems can be monitored, un-monitored, or user-defined. For each monitored or user-defined data system, you configure a connector that Securiti uses to interact with the data system.

A specific occurrence of a data system created on Securiti platform to integrate a data system. A data system instance is authenticated and activated to integrate the data system with Securiti and enable data scanning.
