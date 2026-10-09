---
title: "Using File Insights Policies"
slug: "using-file-insights-policies"
updated: 2026-09-22T12:03:26Z
published: 2026-09-22T12:03:26Z
canonical: "helpcenter.securiti.ai/using-file-insights-policies"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Using File Insights Policies

**Scenario**

As a Data Security Officer, you are responsible for identifying and managing files that pose a risk to your organization. Manually tracking risk across thousands of files in multiple data systems is time-consuming and inconsistent. With File Insights policies, you can combine risk factors like file sensitivity, ownership, and access patterns to surface files that match your organization's risk profile, so you can prioritize and respond with confidence.

## Overview

File Insights policies help you identify and manage files that contain sensitive data across your connected data systems. Insights policies surface files that match any combination of risk factors by using metadata collected in the Data Command Graph from scans you run on your data.

> [!NOTE]
> **Note**
> 
> - This policy does not work with the Securiti Sovereign, as it requires integration with the Data Command Graph.
> - File Insights policies support the multi-org feature. For more information, see [Changing your Organization.](/latest/docs/system-settings-managing-organizations)
> - The Data Inventory Sync for data system connectors must be enabled for your tenant to perform any action on File Insights policies.
> - Ensure the required permissions are enabled for your role. For more information, see [Sensitive Data Intelligence Roles and Permissions](/latest/docs/sensitive-data-intelligence-roles-and-permissions).
> - Before configuring a policy, run the required scans to gather metadata for identifying files that match your policy conditions. These may include Data Inventory Syncs, Discovery Scans, and Access Intelligence Scans.

## Interactive demos

These click-through demos show how to perform actions step by step. Click the **Start Demo** button to begin. Then, click the **Next** button or use the **right arrow** key on your keyboard to proceed, and the **left arrow** key to go back. These demos may include screens from multiple features to illustrate the complete procedure.

### File Insights policy for AWS files

See how Securiti lets you create a File Insights policy to identify and manage files in AWS, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/tgbs8tx4o0rm?embed=popup)

### File Insights policy for SharePoint Online files

See how Securiti lets you create a File Insights policy to identify and manage files in Microsoft 365 SharePoint Online, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/q5o3d0ezeotk?embed=popup)

### File Insights policy for Google Cloud Storage files

See how Securiti lets you create a File Insights policy to identify and manage files in Google Cloud Storage, as shown in the demo below.

[Embedded content](https://app.storylane.io/demo/q2g7uilyac4v?embed=inline)

> [!NOTE]
> Note
> 
> To see more demos related to policies, refer to the following help center articles:
> 
> - [Interactive Demos: Discover and Classify Sensitive Data for AWS](/latest/docs/sensitive-data-intelligence-interactive-demos)
> - [Interactive Demos: Discover and Classify Sensitive Data for GCP](/latest/docs/interactive-demos-discover-and-classify-sensitive-data-for-gcp)
> - [Interactive Demos: Discover and Classify Sensitive Data for SharePoint Online](/latest/docs/policies-2)

## Using the File Insights policies page

The File Insights **Policies** page lets you manage and analyze your policies effectively.

- Use the top filters to view policies by **Date Created**, **Data Modified**, **Policy ID**, **Policy Name** and **File Owner**, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-R098JWWU.png)
- You can view the total number of File Insights policies created, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-M1XRD3NC.png)
- Use the **Column Selector** to include or exclude columns such as **Policy ID**, **Policy Name**, **Files**, **Total Volume**, and so on, as shown below. ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-22W5I4M6.png)
- Click **Files** under the **Data Scope** column to view scoped files in **Graph Explorer**, as shown below. For more information, see [Using Data Command Graph](/latest/docs/using-data-command-graph). ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-4NVTYNO7.png)
- Click **Show Policy Metadata** and select **Explore** to view file relationships in **Graph Explorer**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-B8SR9PZA.png)
- From the options menu (three dots) on the right side of a policy entry, you can **View**, **Edit**, **Clone**, **Delete** or **View in Dashboard** the policy, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-RJ4GK2J3.png)
- Drag the column resize handle to view complete information in any column, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(573).png)
