---
title: "Applying and managing protected MIP sensitivity labels"
slug: "applying-and-managing-protected-mip-sensitivity-labels"
status: "update"
updated: 2026-09-22T08:04:31Z
published: 2026-09-22T08:04:31Z
canonical: "helpcenter.securiti.ai/applying-and-managing-protected-mip-sensitivity-labels"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Applying protected Microsoft Purview Information Protection sensitivity labels

**Scenario**

As a Data Security Officer, you are responsible for ensuring sensitive files carry the correct protection wherever they're stored or shared. Confirming that protection travels with a file outside your original data system, and tracking which files still need a protected label applied, is hard to verify manually across thousands of files. With protected Microsoft Purview Information Protection sensitivity labels, you can apply and monitor encryption-backed labels across your connected data systems, so you can confirm sensitive files stay protected no matter where they end up.

Microsoft Purview Information Protection (MIP) sensitivity labels can be configured with protection to protect files at the file level. Unlike unprotected sensitivity labels, protected sensitivity labels enforce access permissions that remain with the file regardless of where it is stored or shared. Securiti integrates with Microsoft Purview Information Protection to let you view, apply, and manage protected sensitivity labels across supported data systems.

## Prerequisites

Before you apply protected Microsoft Purview Information Protection sensitivity labels, ensure the following prerequisites are met:

- You have configured and authenticated the Microsoft Purview Information Protection connector. For more information, see [Connecting Microsoft Purview Information Protection with Securiti.](/latest/docs/new-ui-connecting-microsoft-purview-information-protection-with-securiti)
- If you authenticated the Microsoft Purview Information Protection connector before Securiti release 1.148, you must reauthorize the connector to use protected sensitivity labels. Reauthorization grants the required **Azure Rights Management Service (RMS)** `Content.SuperUser` permission, which lets Securiti decrypt protected files so that existing protected sensitivity labels can be changed or removed. You do not need to reauthorize the connector if you use only unprotected sensitivity labels. For more information, see [Microsoft Purview Information Protection](/latest/docs/microsoft-purview-information-protection-connectors).
- You have configured the sensitivity label's access control settings using **Assign permissions now** in Microsoft Purview. Securiti does not support sensitivity labels configured with the **Let users decide** option.
- To use the protected Microsoft Purview Information Protection sensitivity labels, you must use pod version 1.150.0 or above.
- For Microsoft 365 SharePoint Online and Microsoft 365 OneDrive, you must enable the metered `assignSensitivityLabel` Microsoft Graph API to update sensitivity labels on files that are already protected. To set up the `assignSensitivityLabel` API, see [Enable metered APIs and services in Microsoft Graph](https://learn.microsoft.com/en-us/graph/metered-api-setup?utm_source=chatgpt.com).

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

## Protected labeling support by file format

Securiti supports protected Microsoft Purview Information Protection (MIP) sensitivity labeling for specific file formats through Data Labeling policies. The support depends on both the file format and the connected data system. For more information about the supported file formats and data systems, see [Protected labeling support by file format](/latest/docs/protected-labeling-support-by-file-format).

## Applying protected sensitivity label

Applying a protected Microsoft Purview Information Protection sensitivity label to a file follows the same process as applying an unprotected sensitivity label. For more information, see [Viewing and syncing classification labels](/latest/docs/viewing-and-syncing-classification-labels).

## Viewing protected sensitivity labels

To view the protected Microsoft Purview Information Protection sensitivity labels:

1. From the upper left corner, click the jewel icon to open the main menu, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-K0I38AN1.png)
2. Click **Settings**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-LOYSHU4W.png)
3. Navigate to **Policy Center** > **Sensitivity Labels** > **Microsoft Purview Information Protection**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-BJD6D773.png)
4. Apply the filter `Protection = Enabled` to see all the protected Microsoft Purview Information Protection sensitivity labels, as shown below. These labels have protection settings enabled and encrypt the file when applied. For more information, see [Viewing and syncing classification labels](/latest/docs/viewing-and-syncing-classification-labels).

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-CGX5HXKS.png)

## Viewing policies with protected sensitivity label on the Data Labeling policy page

To view policies that have a protected Microsoft Purview Information Protection sensitivity label applied on the Data Labeling Policies page:

1. Click **Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-AMHVV43X.png)
2. Click **Data Labeling Policies**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-O1FY7MBQ.png)
3. Click the **Column Selector**, enable **Protected Label** column, and click **Apply**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-JO31MCJP.png)
4. In the **Protected Labels** column, you can see which policies have protected label applied and which do not, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-VCA6BA3S.png)

## Viewing protected files from the Data Remediation dashboard

To view protected files from the Data Remediation dashboard:

1. Navigate to **Data Remediation** > **Data Labeling**, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-X8NWLY8K.png)
2. Apply the filter `Protected by Label = True` to see all the files protected by a protected Microsoft Purview Information Protection sensitivity label, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image-WJ657I11.png)
