---
title: "Exporting and importing DSR forms"
slug: "exporting-and-importing-dsr-forms"
updated: 2026-08-09T18:01:24Z
published: 2026-08-10T21:00:09Z
canonical: "helpcenter.securiti.ai/exporting-and-importing-dsr-forms"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Exporting and importing DSR forms

You can export and import DSR forms between environments. This feature lets you migrate DSR forms without manual setup, maintain consistent templates across tenants, and back up or update forms quickly.

After an export or import attempt, Securiti emails you:

- For export, a zip file containing all exported forms in JSON format.
- For import, a report showing which forms were imported successfully and which were skipped due to misconfigurations.

To export a DSR form:

1. In the Data Subject Rights module, choose **Settings > Form Builder**.
2. On the Form Builder, mark the checkbox next to the forms that you want to export and click **Export Forms**.

![Screenshot_2025-07-28_at_4_03_32_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d27a34b3-5574-2f30-3b7f-c0d52f592dc8.png)

> [!NOTE]
> **Note**
> 
> You can export up to 30 forms at a time. To export more than 30, repeat the export process in batches of 30.

When you export forms, Securiti sends you an email with a download link. Click the link to download a ZIP file that contains one JSON file for each exported DSR form.

![Screenshot_2025-08-03_at_7_58_41_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ca5b89d3-d205-9cdf-2c5a-a1e049079011.png)

Once you have successfully exported forms you can easily import them to a different environment or tenant.

> [!WARNING]
> **Important**
> 
> Before importing, make sure the target tenant or environment has the same configuration for the following elements:
> 
> - **Data systems**: the name (label) and configuration type ID must match exactly, including case and special characters.The Data Subject must have “include this instance in the DSR workflow” checkbox enabled under **Permissions** tab.
> - **Workflows**: the name (label) and configuration for the data systems included in the workflow must be identical to those in the source environments. Moreover, the workflow must be active and has a DSR trigger node.
> - **Task templates**: the name (label) must be the same including case and special characters.
> - **Custom request type**: the value (Request Type Value) must be the same.
> - **Sequential task processing**: If any task template referenced in a sequential rule's execution blocks is missing in the target tenant, Securiti imports the rule as a non-sequential rule instead, with all levels and conditions removed, rather than importing a partial sequence.

To import a form(s):

1. In the Data Subject Rights module, choose **Settings > Form Builder**.
2. At the upper right corner, click **Import Form**.

![Screenshot_2025-07-28_at_4_26_19_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa2576cb-afaf-6cc8-94a9-11ce177f3009.png)
3. Do one of the following:
  - To upload new forms click **New Form** card and upload a JSON file or a ZIP file.

> [!NOTE]
> **Note**
> 
> If the multi-select organization feature is enabled and you can view forms from multiple organizations, you must specify the organization where you want to create the form.
  - To update an existing form click **Update Existing Form** card, upload a JSON file, and select the form you want to update from the menu.

![Screenshot_2025-07-28_at_8_53_06_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7e1a012-1cc6-7d32-d829-f2cd9099a6af.png)

> [!NOTE]
> **Note**
> 
> Observe the following caveats:
> 
> - The imported file must have the same structure as the exported one. The maximum file size for import is 100 MB. You can import JSON or ZIP files to create new forms, but for updating an existing form, upload a single JSON file only.
> - In rectification settings, custom rectification fields do not appear if they are missing in the target tenant or have different names.
> - Under **Automation** in the DSR form builder, if a form includes workflows or data systems that are not found in the target tenant, the associated checkboxes remain selected. The user must manually disable these checkboxes or add the missing workflows or data systems to publish the form successfully.

Once you import a file, Securiti schedules the import and informs you via email when the import is successful. The email also includes an import report with details of skipped elements and their reasons.

When a form is updated, the existing form owners remain unchanged, and the user updating the form is added as co-owner.
