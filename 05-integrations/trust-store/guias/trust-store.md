---
title: "Trust Store"
slug: "trust-store"
updated: 2026-09-15T13:18:20Z
published: 2026-09-22T03:45:42Z
canonical: "helpcenter.securiti.ai/trust-store"
area: integrations
modulo: trust-store
tipo: guia
data_captura: 2026-10-08
---

# Trust Store

The Trust Store page in **Integrations** lets you import and manage CA certificates used to establish secure connections with external systems.

Securiti uses certificates in the trust store to validate SSL/TLS connections for supported integrations. This page provides centralized visibility into all configured certificates, including their status and expiration details.

You can do the following using this page:

- Import CA certificates
- View certificate status (Valid or Expired)
- Monitor expiration dates
- Filter and search certificates

To access the **Trust Store** dashboard:

1. From the upper left corner of the left navigation bar, click the **Jewel** icon, and choose **Integrations** from the left navigation bar.
2. From the left menu of the **Integrations** page, select **Trust Store**.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.18.25 AM.png)

The dashboard displays a summary count and a table of all certificates in your tenant. The page provides the following capabilities:

- A table view for all certificates.
- Summary metrics displayed at the top of the grid that show count for **Configured Certificates**, **Valid Certificates**, and **Expired Certificates.**
- A search bar to search certificates by name or domain.
- A top-level filter that lets you search certificates by the status and expiration date.
- A **Save View** button that lets you save the current filter and search combination as a named view.
- A **Saved Views** button that lets you apply a view you saved earlier.
- A **Column Selector** that lets you include or exclude specific columns, and rearrange their order for custom viewing. It also contains a **Restore Default** button that lets you reset the custom layout back to the original one.
- An **Import CA Certificate** button that lets you upload certificates.

![Upload interface for certificates with options for file formats and size limits.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/truststore_upload.png)

## Understanding the table view

Each row in the table represents a single certificate file. Key columns include:

| Column | Description |
| --- | --- |
| Certificate Name | Displays the uploaded certificate name, such as `jira_certificate.pem` |
| Domain | Displays the associated domain for certificate, if available. |
| Status | Displays the **Valid** or **Expired** status of a certificate. |
| Expiration Date | Displays the certificate expiration timestamp. |

> [!NOTE]
> **Note**
> 
> You can remove columns using the column selector. Securiti adds a horizontal scrollbar automatically as the number of columns increases.

- To delete a certificate, click options (three dots) and select **Delete Certificate**.

![Overview of certificate management with options to delete expired certificates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/truststore_deletecert.png)

## Filtering and searching certificates

Use the search bar at the top of the grid to quickly locate certificates by name or domain.

![Integration settings showing valid certificate for cyberark.local in Trust Store section.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/truststore_search.png)

To narrow down the results, use the top-level filter to focus on specific certificates or filter them by a property.

![Filter options for certificate status and expiration dates in the Trust Store interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/truststore_filters.png)

The top-level filter supports filtering by the following properties:

| Property | Description |
| --- | --- |
| Status | Lets you filter certificates by their status, such as **Valid** or **Expired**. |
| Expiration Date | Lets you filter certificates by their expiration date |

#### Saving and reusing filter views

A saved view stores the filters and the search term you apply to the grid, under a name that you choose. Saving a view lets you return to a filter combination you use often, without building it again.

> [!NOTE]
> Note
> 
> The Save View option is disabled until you apply at least one filter or a search term.

**Saving a View**

1. To save a view, on the **Trust Store** page, apply the filters you want to reuse.
2. At the right end of the filter row, click **Save View**.
3. On the **Save View** popup, enter a **Group**, **Name**, and **Description** for the view and click Save, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.24.08 AM.png)

Securiti adds the view to the **Saved Views** list for the Trust Store page.

**Using a Saved View**

1. To apply a saved view, on the right end of the filter row for **Trust Store** page, click **Saved Views**.
2. On the **Saved Views**, click the view you want to apply.

Securiti loads the saved filters into the filter row, and the grid shows the matching connectors.
3. To view or delete a saved view, from the Saved Views list, click More Actions (three dots) for that view, then click Edit or Delete, as shown below.

![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-09-14 at 11.25.51 AM.png)
