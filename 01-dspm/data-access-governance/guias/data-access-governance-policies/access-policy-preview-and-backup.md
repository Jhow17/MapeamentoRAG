---
title: "Access Policy Preview and Backup"
slug: "access-policy-preview-and-backup"
updated: 2026-08-18T11:00:42Z
published: 2026-08-18T11:00:42Z
canonical: "helpcenter.securiti.ai/access-policy-preview-and-backup"
area: dspm
modulo: data-access-governance
tipo: guia
data_captura: 2026-10-06
---

# Access Policy Preview and Backup

You can Preview the changes the policy will make to the access configurations of your data systems prior to the enforcement of the policy. For each of the policy, that you create, update, or delete, Securiti creates backups automatically, and you can restore to any backup to roll back to that specific state. These controls let you enforce the data access control policies on your data systems in a secure manner, ensuring that you realize the impact of the policies before enforcement.

#### Policy Preview

Securiti supports the following systems for Policy Preview and Backup:

- Databricks
- Snowflake
- Google BigQuery

When you click **Create Policy** button, the **Policy Preview** will be generated. Policy Preview presents you with the entities such as Databases, Tables, Columns, etc., and privileges, row filters, and masking functions that will be implemented upon successful enforcement of the policy. Note that the policy execution will start only if you **Accept** the Policy Preview.

![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e(3).png)

> [!NOTE]
> **Note**
> 
> No backup will be created in the case of the preview being rejected in policy creation.

If you accept the **Policy Preview**, the backup of the policy will be automatically generated and you can access it via **Backups** page. Securiti also generates Policy Preview and Backup when you update or delete the access control policies.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NUWFO00A.png)

#### Access Policy States

Access Control Policies could have the following States:

| Category | Policy State | Description |
| --- | --- | --- |
| Editable States(Policies can be edited) | Created | Policy is created but not yet applied. |
| Evaluated | Policy has been successfully evaluated for a data system for which Policy Preview is not supported. |
| Failed In Evaluation | Policy could not be evaluated due to an error. |
| Failed In Preview Generation | Policy Preview could not be generated for data systems(For data systems supported for Policy Preview). |
| Preview Rejected | User rejected the generated preview. |
| Preview Executed | User accepted the preview; policy applied to the preview supported connector. |
| Graph Not Ready | Data Command Graph is not ready for processing. |
| Non-Editable States(Policies cannot be edited) | Evaluating | (Non-Preview) Policy evaluation is in progress. |
| Generating Preview | Preview is being generated after policy creation (For data systems supported for Policy Preview). |
| Preparing for Execution | The system is preparing to apply the policy. Preparing Payload for evaluation. |
| Evaluating for Execution | The system is validating before applying the policy. Evaluating the preview before executing on the data system. |
| Executing Preview | Preview execution is in progress on the data system. |
| Not In Use | Data system instance is deleted; Policies in Evaluated State transition into “Not in use.” |
| Preview Ready | Preview supported connector preview successfully generated and available for review. |

#### Backups

This section describes the configuration steps for creating a policy Backup manually and restoring a Backup.

### Creating a Policy Backup manually

To create a Policy Backup:

1. In Securiti, click the **Jewel Icon**, then choose **Policies**>**Data Access Control**.
2. Click on the three dots near the upper right corner of the page, then click **Backups**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6FHPOIIL.png)
3. Near the right corner of the page, click **Manual Backup**.
4. On the **Manual Backup** popup, enter the following information
  1. Add **Backup Name** to suit.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RZWWK9WR.png)
  2. Select the data system from the **Data System Type** menu.
  3. From the **Data System** menu, select the Data System instance.
  4. Click, **Create Backup** button.

### Restoring a Policy Backup

To restore a Policy Backup:

1. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-6FHPOIIL.png)
  1. In Securiti, click the **Jewel Icon**, then choose **Policies**>**Data Access Control**.
  2. Click on the three dots near the upper right corner of the page, then click **Backups**.
2. Near the right corner of the user row, click Options (three dots) > **View Backup**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NUWFO00A.png)
3. The Backup Policy page will show you the privileges, row filters, masking functions, and entities included in the backup, when this backup was taken.
4. Near the upper right corner of the page, click the **Restore Backup** button If you want to revert the current state of the data system and restore the data system to the state when this backup was created.

![Restore_backup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-45fb49e9-de41-3f4b-8ef4-9479afa25bd5(3).png)
5. Click the **Restore Backup** button on the confirmation popup to restore the backup. The policies for that particular data system that were not included in the backup that you want to restore to, will be deactivated from the Policies page.

### Policy Backup upon policy deletion

If you delete an active policy, the Policy Preview will be generated. Securiti will not delete the policy instantly, the policy will only delete the policy once you accept the Preview for deletion.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-NUWFO00A.png)![Policy_preview.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-150e7650-4b63-9de0-b869-607808bbd18e(3).png)

Once you **Accept** the **Policy Preview**, the execution will start, and the policy will be deleted from the **Policies** page. Securiti automatically takes the backup for the policy. In the Backup Preview, you will not see any privilege rules, row filters, and masking applied on entities affected by the deleted policy, as there are no active privileges, filters, and masking conditions defined on these entities currently.
