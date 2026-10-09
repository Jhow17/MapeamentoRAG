---
title: "Creating a Data Labeling policy for Google Drive"
slug: "creating-data-labeling-policy-for-google-drive-files"
updated: 2026-09-24T02:54:15Z
published: 2026-09-24T02:54:15Z
canonical: "helpcenter.securiti.ai/creating-data-labeling-policy-for-google-drive-files"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Creating a Data Labeling policy for Google Drive

> [!WARNING]
> Important
> 
> Securiti has deprecated data labeling V1 (rule based) policies. Existing V1 policies remain view-only, and you cannot create, edit, deactivate, or run V1 labeling policies.
> 
> All new data labeling policies must be created using V2 (graph query based) policies. If you need to update a labeling rule, recreate the policy as a new V2 labeling policy by referencing the configuration of the existing V1 policy.

## Overview

Securiti Data Labeling policy integrates with Google Drive labels to enable organizations to define labeling policies based on data discovery and classification results. These policies automatically apply sensitivity labels and metadata to files in Google Drive, helping organizations identify sensitive information and support Data Loss Protection (DLP) services in securing file access and movement.

Google Drive supports up to five labels per file, and each Securiti data labeling policy can apply one label to a file. To apply multiple labels to a file, you can configure multiple policies, each targeting a specific labeling requirement.

During policy creation, Securiti fetches file metadata from Google Drive by retrieving all published labels and making the relevant fields available for use in data labeling policies.

For more information, see [Get started as a classification labels admin](https://support.google.com/a/answer/9292382?src=supportwidget0&amp;hl=en&amp;authuser=0).

> [!NOTE]
> Note
> 
> - When you enable auto labeling, your Data Labeling policies run every 24 hours after you create or modify a policy. The time required to complete labeling depends on factors such as system load, data volume, and policy complexity. With a light system load and a small number of files, labeling may complete almost instantly. With a heavy system load or large datasets, labeling may take several minutes to several hours.
> - You can use Data Labeling policies with the DSPM Enterprise + package. You must have this subscription to access Data Labeling policies.

## Supported data system types

You can create a data labeling policy for [G Suite Google Drive](/latest/docs/g-suite-google-drive-connectors) (Self-hosted) data system type.

## Prerequisites

- To collect the metadata in the graph for use in data labeling policies, you must create and run a Discovery Scan before configuring data labeling policies. For more information, see:
  - [Discovery scans](/latest/docs/discovery-scans).
- You must have a G Suite Google Drive (Self-hosted) instance configured. For more information, see [Setting up your Google Drive data system](/latest/docs/g-suite-google-drive-connectors).
- Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).

The following sections cover more prerequisites to create a data labeling policy for Google Drive.

## Configuring label characteristics in Google Drive

Securiti automatically fetches all labels and their related batches from Google Drive to streamline the file labeling process. The labels must meet the following conditions for Securiti to fetch them.

- Securiti only fetches published labels that have the Drive and Docs options enabled in applications, as shown below."

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-22OGFOTZ.png)
- The label fields must also include a badge and an option list (single select), as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-F6ZBT0JZ.png)

You can create multiple labels in Google Drive and assign them desired badges and field names. For more information, see [Create classification labels for your organization](https://support.google.com/a/answer/13127870?src=supportwidget0&amp;hl=en&amp;authuser=0).

## Labeling files in shared drives

Securiti applies labels to files stored in shared drives through the [Google Drive](/latest/docs/g-suite-google-drive-connectors) (Self-hosted). To enable labeling, ensure that at least one member of your organization with access to the shared drive has contributor, content manager, or manager permissions.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JPNTVXX3.png)

> [!NOTE]
> Note
> 
> Securiti does not support labeling on files stored in the shared drive through the [Google Drive cloud connector](/latest/docs/activate-the-g-suite-google-drive-securiti-cloud-connector-in-securiti).

## Setting up Google Drive data system

Securiti lets you apply a data labeling policy to both your Securiti cloud and Google Drive(Self-hosted) data system connectors. To apply the data labeling policy to your Google Drive, make sure your Google Drive connector (Self-Hosted or Cloud) is activated and the relevant permissions are granted, as described below:

1. From the left panel, select **Integrations > Monitored Data Systems**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-62H2Q2QP.png)
2. Apply the filter `Data System Type = Google Drive (Google Workspace) (Self Hosted)` to verify whether your Google Drive connector is activated or requires further action. The results show one of the following:
  - **0 instances**: No active Google Drive connector exists for creating the data labeling policy. To set up a new connector instance, see [Activate the Google Drive (Self-Hosted) connector in Securiti](/latest/docs/activate-the-g-suite-google-drive-self-hosted-connector-in-securiti).
  - **1 or more instances**: Verify the following:
    - The relevant Google Drive instance on which the files need to be labeled is listed.
    - The Google Drive instance has a green tick mark next to it, indicating that it is activated.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GZ76T158.png)
3. Click your instance and go to the **General** tab to verify that the relevant permissions are granted. Locate **Data Labeling Policy** and ensure the **Allow Data Labeling Policy Integration checkbox** is selected, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-GVODHZRZ.png)

## Running a scan on Google Drive connector instance

You must initiate a **Data Scan** for your [Initiate Google Drive (Securiti Cloud) data scanning](/latest/docs/configuring-general-permissions-for-google-drive-google-workspace-self-hosted) or a [Configure discovery scans in Google Drive (Self-hosted)](/latest/docs/configure-discovery-scans-in-g-suite-google-drive-self-hosted-1) and wait till the scan is completed before applying the data labeling policies.

> [!NOTE]
> Note
> 
> - The completion time of the discovery scan depends on the amount of data in your system.
> - When you apply Google labels to files in Google Drive, Google preserves the file's Last Modified timestamp natively.

## Creating a Data Labeling policy for Google Drive

> [!NOTE]
> **Note**
> 
> Securiti lets you apply up to five labels to a file, each applied through a separate policy. If you attempt to apply a sixth label, Securiti displays an error message.

To create a data labeling policy for Google Drive:

1. From the main menu, choose **Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-URFR8B76.png)
2. On the **Policies** page, choose **Data Labeling**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-18UBBBVR.png)
3. Near the upper right corner of the page, click **+ Create**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XRGEDWIA.png)
4. In the **Create a New Policy** popup, select the **Policy Type** and **Data System** **Type**, as shown below, and click **Get Started**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AE1EM2LM.png)
5. Enter a **Name** and **Description** for the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M6MHJL04.png)
6. Set the policy **owner**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-XCCWB0QD.png)
7. (Optional) Set the policy **co-owners**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-9T5BOI6D.png)
8. To activate the Data Labeling policy, turn on the **Activate Policy** toggle, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-8T1K1XU0.png)
9. Securiti automatically chooses the **Integration type** based on the data system selected in the **Create a New Policy** popup.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VSLPXWUJ.png)
10. Choose the Google **Workspace** that is associated with a labeling-enabled Google Drive connector, as shown below. When the policy runs, Securiti loads labels only from the selected workspace and excludes files that belong to other workspaces.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-A0Q3EJ5K.png)

> [!NOTE]
> Note
> 
> - The Google Drive connector must be onboarded using an account that belongs to the primary domain (primary organization) of the selected Google workspace. Accounts from secondary domains (secondary organizations) are not supported for onboarding the connector for labeling policies.
> - If you are creating multiple data systems within a single workspace, you only need to configure data labeling permissions for one data system when creating the data labeling policy. This allows you to label any file within that workspace.
11. In the **Scope** section, click **Edit Query** to add files to your scope, as shown below. This opens the **Graph Explorer**, where you can select the file scope and relevant data elements (such as first name, last name, SSN, and so on). Review the query results carefully to ensure the scoped files match your expectations. Then click **Use Query** to apply the selection. The scope is now defined, and you are returned to the data labeling policy configuration page. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-W8EC3NAC.png)

To learn more about **Graph Explorer**, see the [Graph Explorer](/latest/docs/using-graph-explorer) documentation. Securiti can automatically carry over queries created in Graph Explorer to the policy creation page. For more information, see [Create policies using Graph Explorer](/latest/docs/create-policies-using-graph).
  - You can add the **Files** node as a secondary node when configuring the scope query, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RM6FBZ9Q.png)

> [!NOTE]
> Note
> 
> By default, Securiti applies a `Skipped = False` filter to the scope query in Data Labeling policies. This filter excludes files marked as **Skipped** from the policy scope and prevents them from being labeled.
12. To view the number of files included in the scope, click **Show Impact** in the **Scope** section, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-T0P1MW6F.png)
13. In the Actions section, click **+ Add Actions**, as shown below. You can add one or both of the following actions to the policy:

### Applying a classification label

### Sending an email notification

The **Send an Email Notification** action lets you notify the data system owner, selected users, or both, with a summary of how many files were skipped, failed, or successfully labeled by the Data Labeling policy.
  - **Apply a Classification Label**: Applies a sensitivity label and metadata to the files in scope, based on their classification results.
  - **Send an Email Notification**: Notifies the policy owner or specific users by email about policy events, changes, or activities.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EF95HVO5.png)
  1. To apply a classification label, click **Edit,** as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4QCF9OGV.png)
  2. In the **Label Configuration** section, choose the appropriate **Label Name** and **Field Name**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-10NFN3S0.png)
  3. (Optional) Mark the **Apply a specific label directly to all files** option to assign a single label to all scoped files, as shown below. You can choose one of the following labels:

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-D1LONM0H.png)
    - Critical
    - High
    - Low
    - Public
  4. (Optional) Click **+ Add** to configure **Content Profile Mapping** or **Data Element Mapping**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-3YW8YUM4.png)
    1. Choose one or more **Content Profile(s)** and assign **Sensitivity Label(s)**, as shown below. The **Content Profiles** with higher sensitivity labels are given preference, so the sequence of content profiles selected does not matter. When selecting **Content Profile(s)** you can also choose **Any** or **None**:
      - **Any:** Applies the **Sensitivity Label** if any content profile matches the document. When **Any** is selected, only one mapping is allowed in the policy.
      - **None:** Applies the **Sensitivity Label** if no content profile is matched on the document.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-09AOC3FF.png)
    2. Choose one or more **Data Elements(s)** and assign **Sensitivity Label(s)**, as shown below. The **Data Element(s)** with higher sensitivity labels are given preference, so the sequence of data elements selected does not matter. When selecting **Data Elements(s)** you can also choose **Any** or **None**:
      - **Any:** Applies the **Sensitivity Label** if any data element matches the document. When **Any** is selected, only one mapping is allowed in the policy.
      - **None:** Applies the **Sensitivity Label** if no data element is matched on the document. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AN4T1FLS.png)

> [!NOTE]
> Note
> 
> There is no limit to the number of content profiles and data elements you can add.
  5. In the **Additional Fields** section, choose **Field Name** and enter your desired **Field Value**, to populate the file’s metadata, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BFZR9ZUD.png)
  6. You can also apply **Additional** **File Metadata** such as, **Data Element Categories**, **Data Element Types**, **Document Categories**, **Document Types**, and so on, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-IPN7OWQW.png)
  7. There are two **Labeling Options** available:

| Labeling Options | Description |
| --- | --- |
| **Auto Labeling** | Automatically applies sensitivity labels to files when the policy runs. This options includes the following control: - **Set Scheduler Time:** Specifies the time of day for scheduled auto-labeling in UTC using a 24-hour format (for example, 10:00 or 22:00). If left empty, the policy runs daily at the time the schedule is saved. |
| **Override already applied labels** | Replaces existing sensitivity labels on files with the new labels the policy applies. When the policy runs, Securiti reads each file's current label at run time and uses it as the existing label. This check happens independently of whether Securiti ingests existing sensitivity labels during a discovery scan or data inventory sync. This way, the policy always has the latest label information when deciding whether to label the file. Securiti uses this label for the following control: - **Skip if the new label lowers sensitivity:** Prevents the policy from replacing an existing label if the new label represents a lower sensitivity level. |

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-0BUYK5YP.png)
  1. To send an email notification, click **+ Add Actions** and choose **Send an Email Notification**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-17NOK8C6.png)
  2. (Optional) In the **Send an Email Notification** popup, mark the **Notify store owner** checkbox to send an email notification to the policy owner, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VZRQRCKB.png)
  3. (Optional) To notify additional users, enter their username or email address in the search field and select them from the list. Each added user appears as a tag below the field, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-PBTCXBXG.png)
  4. Click **Save Action**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CM4A2JJ7.png)
14. Click **Create Policy.** Once created, the policy appears on the data labeling **Policies** page, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Y0L57FE7.png)

## Searching labeled documents in Google Drive

To search labeled documents in Google Drive:

1. In your Google Drive console, click the **Advanced Search** icon, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-Q88R47QO.png)
2. Locate the **Labels** field and search for your custom label, as shown below. To further narrow down your search, specify fields and click **Search**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-EME88EPQ.png)

You can see a relevant list of documents to which your custom label was applied.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-L9JPMI9R.png)
