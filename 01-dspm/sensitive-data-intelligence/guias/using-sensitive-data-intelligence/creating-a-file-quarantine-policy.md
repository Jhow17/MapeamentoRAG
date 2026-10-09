---
title: "Creating a File Quarantine policy"
slug: "creating-a-file-quarantine-policy"
updated: 2026-08-20T13:18:10Z
published: 2026-08-20T13:18:10Z
canonical: "helpcenter.securiti.ai/creating-a-file-quarantine-policy"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating a File Quarantine policy

> [!WARNING]
> Important
> 
> Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.

To create a File Quarantine policy:

1. From the main menu, choose **Policies**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-URFR8B76.png)
2. On the **Policies** page, choose **File Quarantine**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-SPKKHC93.png)
3. Near the upper right corner of the page, click **+ Create**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ORN381OL.png)
4. Enter a **Name** and **Description** for the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-TIB88S2Y.png)
5. Set the **Severity** level to calculate the overall data risk score for the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-J2O07WWC.png)
6. Set the policy **owner**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-APLDXRQL.png)
7. (Optional) Set the policy **co-owners**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FYM55DW3.png)
8. To activate the File Quarantine policy, turn on the **Activate Policy** toggle, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RXAGHIFH.png)
9. In the **Scope** section, the **Files** node must include one of the following values for the **Data System Types** property:
  - Azure Data Lake Storage (ADLS) Gen2
  - Microsoft 365 OneDrive
  - Microsoft 365 SharePoint
  - NFS
  - SMB

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IX2669IS.png)
10. In the **Scope** section, click **Edit Query** to add files to your scope, as shown below. This opens the **Graph Explorer**, where you can select the file scope and relevant data elements (such as first name, last name, SSN, and so on). Review the query results carefully to ensure the scoped files match your expectations. Then click **Use Query** to apply the selection. The scope is now defined, and you are returned to the File Quarantine policy configuration page.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-KDI54BIN.png)

To learn more about **Graph Explorer**, see the [Graph Explorer](/latest/docs/using-data-command-graph) documentation. Securiti can automatically carry over queries created in Graph Explorer to the policy creation page. For more information, see [Create policies using Graph Explorer](/latest/docs/create-policies-using-graph).
11. To view the number of files included in the scope, click **Show Impact** in the **Scope** section, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ZI1JL396.png)
12. To add one or more actions, click **+ Add Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YJ4JKTT5.png)

> [!WARNING]
> Important
> 
> - With Securiti release 1.149, the **Quarantine Files Within The Same Data System** action is deprecated for File Quarantine policies. You can continue to use this action; however, we recommend using the **Quarantine Files To A Central Quarantine Destination** action for new policies to take advantage of the latest features and enhancements. For more information, see [Using Central Quarantine Destination](/latest/docs/using-quarantine-destinations).
> - The Quarantine Files Within The Same Data System action is not supported for the following data systems
> 
> To quarantine files in these data systems, use the Quarantine Files To A Central Quarantine Location action.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-YTYELCQ3.png)
>   - Amazon S3
>   - Azure Files
>   - Azure Blob Storage
>   - Azure Data Lake Storage (ADLS) Gen2
13. On the **Quarantine Files Within The Same Data System** popup:

> [!WARNING]
> Important
> 
> Before using the **Quarantine Files To A Central Quarantine Location** action, review the **Key Considerations** in [Using Central Quarantine Destination](/latest/docs/using-quarantine-destinations) for important limitations and behavior.
  1. (Optional) Mark the **Auto Quarantine** checkbox to automatically quarantine files when the policy is activated, and choose one of the following options, as shown below.

| Option | Description |
| --- | --- |
| (Optional) Ignore files reverted by other policies | Mark this checkbox if you want to ignore files that are reverted by other policies. |
| (Optional) Ignore files failed by other policies | Mark this checkbox if you want to ignore files failed by other policies. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-60PT50UF.png)
  2. Schedule the policy to run daily at a specific hour and minute, as shown below. If you leave this field empty, the policy runs daily at the same time you save it.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K76BFD6C.png)
  3. Define the **Quarantine Folder Path** where you want to quarantine your files, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XQBG68YV.png)
  4. (Optional) Mark **Drop placeholder file** checkbox to place a marker at the original file location after quarantine, and add the **Placeholder file text**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IDOSY776.png)
14. On the **Quarantine Files To A Central Quarantine Location** popup:
  1. (Optional) Mark the **Auto Quarantine** checkbox to automatically quarantine files when the policy is activated, and choose one of the following options, as shown below.

| Option | Description |
| --- | --- |
| (Optional) Ignore files reverted by other policies | Mark this checkbox if you want to ignore files that are reverted by other policies. |
| (Optional) Ignore files failed by other policies | Mark this checkbox if you want to ignore files failed by other policies. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-66EWINI6.png)
  2. Schedule the policy to run daily at a specific hour and minute, as shown below. If you leave this field empty, the policy runs daily at the same time you save it.![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-UQ55TXLN.png)
  3. Search for and select the **Quarantine Destination** where you want to quarantine your files, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-ESR1DX2H.png)
  4. (Optional) Mark **Drop placeholder file** checkbox to place a marker at the original file location after quarantine, and add the **Placeholder file text**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4YLY2IOZ.png)
15. On the **Send an Email Notification** popup
  1. Search for the **User(s)** you want to send an email notification to, and select **Notify Store Owner** if you want to notify the store owner.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-FK5WM6IH.png)
  2. Click **Save Action**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IQ94H33F.png)
16. Click **Create Policy.** Once created, the policy appears on the File Quarantine **Policies** page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LZ8PJ1YO.png)
