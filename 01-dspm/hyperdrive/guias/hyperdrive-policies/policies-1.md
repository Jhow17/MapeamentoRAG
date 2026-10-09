---
title: "Hyperdrive policies"
slug: "policies-1"
status: "update"
updated: 2026-09-22T04:22:29Z
published: 2026-09-22T04:22:29Z
canonical: "helpcenter.securiti.ai/policies-1"
area: dspm
modulo: hyperdrive
tipo: guia
data_captura: 2026-10-06
---

# Hyperdrive policies

> [!WARNING]
> Important
> 
> This feature is available in Securiti SaaS deployments but is not currently available in Securiti Sovereign deployments. Contact your Customer Success Manager or Account Representative for updates on its availability in your tenant.

Hyperdrive mode supports large-scale file processing in data system. This mode is designed to efficiently process millions of files across supported data systems.

Hyperdrive mode supports the following policy types:

- **Data Labeling policies**: Lets you apply sensitivity labels to large volumes of files efficiently.
- **File ROT policies**: Lets you identify and process redundant, obsolete, or trivial files at scale.
- **Quarantine policies**: Lets you move scoped files to a Central Quarantine destination using a high-performance execution model.

Use the table below to understand the supported data systems for each hyperdrive policy.

| Hyperdrive policy | Supported data systems |
| --- | --- |
| Data Labeling | - Amazon S3 - Microsoft 365 OneDrive - Microsoft 365 SharePoint Online - NFS - SMB |
| File ROT | - Amazon S3 - Microsoft 365 OneDrive - Microsoft 365 SharePoint Online - SMB |
| Quarantine | - Amazon S3 - Microsoft 365 OneDrive - Microsoft 365 SharePoint Online - SMB |

> [!WARNING]
> Important
> 
> - If the Hyperdrive mode is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to determine if this feature is included in your subscription and if your tenant meets the requirements to use this functionality.
> - Quarantine policies with Hyperdrive mode cannot be used with previously configured Microsoft 365 data system connectors. You must migrate to a tenant with Hyperdrive mode enabled and start a fresh scan for your data systems.
> - Hyperdrive mode works only with the Central Quarantine destination.

To view the created Hyperdrive policies in Securiti:

1. In **Sensitive Data Intelligence > Policies**, from the left menu, select your policy type, such as **File Quarantine.**
2. From the top-level filter of the page, click **+** to open the list of available properties.
3. From the available properties, select **Is Hyperdrive** and set it to **True**, as shown below.

![Filter options for policies, highlighting 'Is Hyperdrive' selection with various policy details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/hyperdrive_ishyperdrive_property(1).png)
4. Click **Apply**.

Securiti displays all the Hyperdrive policies created for a selected policy type.
