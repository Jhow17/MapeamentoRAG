---
title: "Viewing VDC data in Data Command Graph"
slug: "viewing-vdc-data-in-data-command-graph"
updated: 2026-07-30T06:46:06Z
published: 2026-07-30T06:46:06Z
canonical: "helpcenter.securiti.ai/viewing-vdc-data-in-data-command-graph"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Viewing VDC data in Data Command Graph

After you connect and scan your Veeam Data Cloud (VDC) connector, Securiti ingests backup metadata from your VDC tenant into the Data Command Graph. You can then query and explore protected resources, backup coverage, and restore point availability using Graph Explorer and Instance Explorer.

> [!NOTE]
> Note
> 
> Data appears in the Data Command Graph only after a successful data scan has completed for your VDC connector. For more information, see [Initiate data scanning for VDC for M365 connector](https://helpcenter.securiti.ai/docs/en/initiate-data-scanning-for-vdc-for-m365-connector).

VDC data appears in the Data Command Graph under the **Backup** and **Backup Inventory** groups.

## Backup entities

The following entity is populated with the required VDC data in the **Backup** group:

| Entity | Description |
| --- | --- |
| Restore Point | Represents a specific backup snapshot available for a protected resource. Use this entity to determine whether a resource can be reverted to a previous state following a destructive action. |

## Backup Inventory entities

The following entities are populated with the required VDC data in the **Backup Inventory** group:

| Entity | Description |
| --- | --- |
| Protected Drive | Represents a OneDrive account protected through Veeam Data Cloud. Use this entity to assess whether a user's drive data has backup coverage before or after an activity event. |
| Protected Mailbox | Represents a mailbox protected through Veeam Data Cloud. Use this entity to review protection status when investigating mailbox-related activity. |
| Protected Team | Represents a Microsoft Teams environment protected through Veeam Data Cloud. Use this entity to evaluate backup alignment when reviewing team-level activity. |
| Protected Site | Represents a SharePoint site protected through Veeam Data Cloud. Use this entity to correlate activity with backup coverage at the site level. |
| Protected Object | Represents a generic protected asset within the backup inventory, used when the object doesn't map to a more specific entity type such as a file, drive, or mailbox. |
| Application | Represents a specific backup snapshot available for a protected resource. Use this entity to determine whether a resource can be reverted to a previous state following a destructive action. |
| VDC Data System | Represents the Veeam Data Cloud data system associated with a protected resource, representing the connection between the graph and a customer's VDC organization or tenant. |
| File Item | Represents an individual file discovered in, or backed up from, a protected data system. |

## Relationships for protected entities

You can explore the following relationships for your Protected Resource or Restore Point entity in Graph Explorer:

| Relationship | From entity | To entity | Description |
| --- | --- | --- | --- |
| Has data system | Protected Object | VDC Data System | The relationship shows the VDC data system associated with the backup resource. |
| Has restore point | Protected Object | Restore Point | The relationship shows the restore points available for the backup resource. |
| Has backed up drive | User Principal | Protected Drive | The relationship shows the OneDrive accounts backed up for a given user. |
| Has backed up mailbox | User Principal | Protected Mailbox | The relationship shows the mailboxes backed up for a given user. |
| Has backed up team | M365 Team | Protected Team | The relationship shows the Teams environments backed up for a given team. |
| Has backed up site | Site | Protected Site | The relationship shows the SharePoint sites backed up for a given site. |

## Example - Checking backup coverage before reverting a file

To confirm that a restore point exists for a specific user's OneDrive before initiating a revert, create the following query:

1. In Graph Explorer, select **Protected Drive** from the **Backup Inventory** group.
2. Add a relationship to **Restore Point** to view available backup snapshots for each protected drive.
3. Filter by **Backup Time** property to identify snapshots captured before the event you want to revert, as shown below.

![Graph Explorer interface showing restore points and backup times for Protected OneDrive.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/restoreandbackupquery.png)
4. Use the Undo AI capability in the Agent Activity Overview dashboard to initiate the revert. For more information, see [Using Agent Activity Overview dashboard](/latest/docs/agent-activity-overview-dashboard#undo-ai-actions-using-restore-points).
