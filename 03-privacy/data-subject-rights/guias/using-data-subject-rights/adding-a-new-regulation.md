---
title: "Adding a new regulation"
slug: "adding-a-new-regulation"
updated: 2026-01-14T09:39:10Z
published: 2026-01-14T09:39:10Z
canonical: "helpcenter.securiti.ai/adding-a-new-regulation"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Adding a new regulation

You can add a regulation if out-of-box regulations don’t meet your organization’s needs.

> [!NOTE]
> Note
> 
> Only Super Admins in your Securiti tenant can add or update regulations. All other roles, except guest users, have read-only access to this page. You can configure regulations at the tenant level, ensuring they apply across all organizations. While you can switch between organizations, the regulations remain consistent across all organizations within the same tenant.

To add a new regulation:

1. From the Regulations Support dashboard, at the upper right corner click **+ Add New Regulation**.
2. On Add Regulation popup, fill the following information:

| Regulation Name | Enter the name of regulation. It must be unique. The max character limit is 400 including numbers and special characters. |
| --- | --- |
| Region | Select the region from the menu. |
| Country | Select the region or continent where the regulation applies |
| State/Province | Select the specific state or province where the regulation applies. If the regulation applies to the entire country, select **All** from the menu. |
| Default Regulation for this Jurisdiction | Select this checkbox to set the regulation as the default for the jurisdiction defined by a unique combination of country and state or province. This setting is used when IP or country and state-based geolocation is configured in a DSR form to automatically detect and apply the correct regulation. Only one default regulation can exist for each jurisdiction. Selecting this checkbox overrides the previous default for the same jurisdiction. System Behavior: - Every jurisdiction always has one default regulation. When you create a new regulation, if the **country and state or province combination** for that regulation does not already have a default regulation, Securiti automatically marks the new regulation as the default for that jurisdiction. - If a regulation is created and marked as default for a jurisdiction that already has one, the existing default regulation is automatically unmarked. - When a data subject submits a DSR form, Securiti detects the location (through IP address or through the country and state provided) and applies the default regulation for that detected location. - If both a country-level regulation (State/Province = All) and a state-level regulation (for example, Saudi Arabia – Riyadh) are set as default, the state-level regulation applies when the detected location matches that state, while the country-level regulation remains default for other states. - If no jurisdiction-level default matches, Securiti checks for a country-level default (where State/Province = All). - If neither is found and the detected region is Europe, Securiti defaults to GDPR. - If all checks fail, Securiti uses system default values (not user-modified). These include a 45-day response duration, automatic extension enabled (45 days), and appeals disabled. |
| Industry | Select the industry from the menu where the regulation applies, such as Commercial, Education, or Financial. Select All if the regulation applies to every industry. |
| Deadline | Enter the response deadline in days. The maximum value is 1000 days. |
| Extension Supported | Turn on this option if the regulation supports deadline extensions. |
| Extension Period | Enter the extension period in days. The value must be between 1 and 365 days. |
| Appeal supported | Turn on this option if the regulation supports appeals. **System Behavior:** - When an appeal is created for a request submitted through an auto-detect IP or location-based DSR form, Securiti uses the derived jurisdiction (the regulation determined during request creation) and fetches all appeal-related settings from the centralized regulation table. - If appeals were supported when the request was created, but the same regulation is later updated to not support appeals, Securiti still creates the appeal with a response duration of 0 days. - If a regulation supports appeals in the Regulations Support dashboard and the same regulation is used in a DSR form that is configured to auto-detect based on country, state, or IP, you must also select the **Enable Appeals** checkbox in the DSR form configuration. In this scenario, appeals work only when both the regulation and the DSR form have appeals enabled |
| Appeal Deadline | Enter the appeal deadline in days. The maximum value is 1000 days. |
| Appeal Extension | Enter the extension period in days. The value must be between 1 and 365 days. |
3. Once done, click **Add.**

### Automatic DSR form creation for new tenants and privacy centers

**For new tenants or organizations:**

When a new tenant or organization is created, Securiti automatically creates and publishes three DSR forms: CPRA, LGPD, and Internal.

Each form is created using regulation data fetched from the Regulations Support dashboard. Securiti uses the most recent configuration for each regulation, whether Standard or Customized, ensuring that all newly created forms reflect the latest compliance settings.

**For Privacy Center setup:**

When setting up a new Privacy Center, Securiti uses the Country and State/Province selected in the setup form to determine the applicable regulation.

The system checks regulations in the following order:

- Exact match – Finds a regulation where both country and state/province match the selected values.
- Country-level match – If no exact match exists, it looks for a regulation where the selected country matches and State/Province is set to All.
- Default regulation – If neither condition applies, the system defaults to U.S. California (CPRA).

If the CPRA regulation has been customized, the Privacy Center uses the customized configuration. Otherwise, it uses the standard CPRA configuration. Securiti automatically creates and associates a DSR form based on the detected regulation to the privacy center, including all applicable deadlines, request types extension settings, and appeal rules defined in the **Regulations Support** dashboard.

### Editing a regulation

You can edit a regulation to update specific configurable settings, such as the deadline, extension, or appeal options. To edit a regulation:

1. On the **Regulations Support** dashboard, at the end of the regulation row, click **More Actions** (3 dots) > **Edit Regulation**.

![Table displaying regulations with details on regions, deadlines, and applicable locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-08 at 6.43.02 AM.png)
2. In the Edit Regulation popup, review the regulation details.
  - Most fields, such as Regulation Name, Region, Country, State/Province, and Industry, are locked and cannot be edited.
  - ​​You can update the Deadline, Extension supported, and Appeal supported fields.
  - The Default regulation for this jurisdiction checkbox may appear in two states:
    - **Grayed Out**: When there is only one regulation for that jurisdiction, the checkbox cannot be changed.
    - **Editable**: When multiple regulations exist for the same jurisdiction. In this case, one regulation is already marked as default (grayed out), and the other can be selected.
    - If you mark the checkbox for another regulation, Securiti automatically unmarks the existing default regulation for that jurisdiction.
3. Click **Save** to apply the changes.

![Editing regulation details including deadlines, extensions, and appeal options for jurisdictions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-08 at 6.44.38 AM.png)

After saving, the Associated DSR Forms dialog appears. It lists all DSR forms affected by the regulation changes. You must review each listed form, make the required changes, and then republish it.

![List of DSR forms with publication status and modification confirmation message displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-08 at 7.19.13 AM.png)

### Revert to default

You can revert a customized regulation to its standard configuration.

To revert a regulation to default:

1. On the **Regulations Support** dashboard, locate the regulation where the **Source** is marked as **Customized**.
2. At the end of the regulation row, click **More Actions** (3 dots) > **Revert to Default**.

![Overview of data subject rights regulations with highlighted access request type.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2025-12-08 at 3.03.21 PM.png)
3. In the confirmation dialog, click **Yes, Revert** to restore all values to the default configuration of the standard regulation. When you revert a customized regulation to default, the regulation’s Source changes from Customized to Standard. This indicates that the regulation has been restored to its original system-provided configuration.

After reverting, the Associated DSR Forms dialog appears. It lists all DSR forms affected by the regulation changes. You must review each listed form, make the required changes, and then republish it.

> [!WARNING]
> Important
> 
> - The Revert to default option is available only for regulations that originate as standard but have been customized. The option is not available for User Defined or Standard regulations.
> - When you revert a customized regulation to default, its Source changes from Customized to Standard. Manually restoring values to match the default does not change the Source automatically. For instance, if the standard Deadline is 45 days and you change it to 46, the Source becomes Customized. Setting it back to 45 and saving does not make it Standard again. The Source changes to Standard only after you click Revert to Default and confirm
