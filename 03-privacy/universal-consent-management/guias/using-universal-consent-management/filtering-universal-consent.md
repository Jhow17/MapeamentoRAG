---
title: "Filtering universal consent records in the Legacy Dashboard"
slug: "filtering-universal-consent"
updated: 2026-03-05T09:30:26Z
published: 2026-03-09T21:35:07Z
canonical: "helpcenter.securiti.ai/filtering-universal-consent"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Filtering universal consent records in the Legacy Dashboard

You can use these filters on the Universal Consent dashboards to quickly focus your view of the current data based on various criteria. Where available, the filter tools are always located in the upper right corner of the page, as shown below.

![UCM-Dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6a27f5b2-e48e-da1d-9f36-8b4410505ca8.png)

You can save the filters once you apply them and later load them as described in [Using saved filters](/latest/docs/filtering-universal-consent#using-saved-filters).

Universal Consent Management filters:

| Filter | Purpose |
| --- | --- |
| Date Created | Mark the radio button for any one of the different time options to filter out consent records with respect to the date when they were created in Securiti, as shown below. ![UCM-Date-Created-Filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3d59e1ef-f07a-2751-f410-2c51b929967f.png) |
| Derived Consents | Mark the checkbox against to one or more derived consents to filter consent records by the following statuses. - Default Consent State - B2B - Existing Business Relationship - Reasonable Expectations - Distributorship Agreement - Publicly Available Contact Information ![UCM-Derived-Consent-Filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-012f0568-6ac4-a749-61d5-c893bdffb22a.png) |
| Consent Status | Mark the checkbox against one or more of the consent statuses to filter out consent records with the following statuses. - Granted - Declined - Withdrawn - Pending - No Consent > [!NOTE] > **Note** > > The No Consent state only belongs to the Explicit Consent preference center. When your data subjects click **Submit** via the Explicit Consent preference center without giving any consent, we record this action as **No Consent**. |
| Source | Mark the checkbox against one or more of the following sources to filter out consent records that came in the system via these sources. - Form - Preference Center - Consent API - Consent Narrow Path - Platform Integrations |
| Consent Collected | Mark the radio button for any one of the different time options to filter out consent records with respect to the date when they were uploaded by you in Securiti, as shown below. ![UCM-Consent-Collected-Filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-64a17255-4b9c-22d4-544c-a92ee888e127.png) |
| Processing purpose | Use this field to filter out consent records by the name a specific Processing Purpose. |
| Consent purpose | Use this field to filter out consent records by the name of a specific of Consent Purpose. |
| Processing purpose category | Use this to filter out consent records on the basis of Processing Purpose Category. |
| Country | Select one or more country names from the menu. |
| Subject Identity | Add the **Subject Identity** value such as email, phone, customer ID, first name, or last name in their respective fields to filter consents from the Consent Records table, as shown below. ![filtering_ucm_records.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-964c80fa-4694-ff61-2344-ebcb63b89c1e.png) |

## Using saved filters

After you apply filters as described above, you can save the filter configuration and load it again later. This feature makes it easy re-apply specific filter sets to your view of the current data. See the following sections for details.

### Saving and loading filters

To save a filter configuration:

1. Apply a set of filters as described above.
2. At the top of the filter panel where it lists the number of active filters, click menu (hamburger icon) and then **Save filter as**, as shown below.

![Dashboard displaying consent overview, status, and filter options for user consent management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_save_filter_1.png)
3. On the **Save New Filter** panel, enter a name. You can also enter an optional description that helps you remember the filter.

![Dashboard displaying consent statistics and options for saving new filters.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_save_filter_2.png)
4. Click **Save**, as shown below.

![Dashboard displaying consent statistics and filter options for user preferences.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_save_filter_3.png)

Securiti shows you the saved filter name on the filter banner.

To load a filter configuration that you have previously saved:

1. In the Universal Consent Dashboard, open the filter panel.
2. On the active filter banner just below the top of the filter panel, click menu (hamburger icon) and then **Load Filters**, as shown below.

![Dashboard displaying consent statistics, including granted, declined, and residency data.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_load_filter_1.png)
3. Choose the filter from the menu, click **Done,** and apply it.

![Dashboard displaying consent overview, status, and filter options for user consent management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_load_filter_2.png)

### Modifying a saved filter

To modify the saved filter:

1. Load the filter you want to modify as described in [Saving and loading filters](/v1/docs/filtering-universal-consent#saving-and-loading-filters).
2. Use the filters panel to add or modify filter criteria.

After you make changes, Securiti shows a warning icon on the banner to show that the current filter settings differ from the saved filter.
3. From the menu, click **Save**.

![Dashboard displaying consent statistics and filter options for user management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_modify_filter_1.png)

Securiti updates the saved filter to match the criteria you selected.

### Cloning a filter

To clone a filter:

1. Load the filter you want to clone as described in [Saving and loading filters](/v1/docs/filtering-universal-consent#saving-and-loading-filters).

Securiti shows you the filter name on the filter banner.
2. Change the filter criteria to suit.
3. From the menu, click **Clone saved filter**.

![Dashboard displaying consent status, filters, and consent overview for user management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_clone_filter.png)
4. On the **Save New Filter** panel, give the clone a new name and description, and click **Save**.

![Dashboard displaying consent status, filter options, and consent overview metrics.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_clone_filter_2.png)

### Detaching a saved filter

Detaching filter criteria from a saved filter makes it easier for you to create a new filter based on the settings of a previously saved filter.

1. Load the filter you want to detach as described in [Saving and loading filters](/v1/docs/filtering-universal-consent#saving-and-loading-filters).

Securiti shows you the filter name on the filter banner.
2. From the filter menu, click **Detach from saved filter**.

![Dashboard displaying consent status, overview, and filter options for user consent management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ucm_detach_filter.png)

Securiti detaches the criteria from the saved filter, and removes the filter name from the banner to show you that the current filter criteria are separate from any saved filter.
3. Change the filter criteria to suit.
4. If you want, save the filter as described in [Saving and loading filters](/v1/docs/filtering-universal-consent#using-saved-filters).

Processing purposes are the purposes for which organizations or businesses process personal data belonging to their data subjects.

Consent purposes are purposes for which organizations or businesses process personal data for individual actions and tasks to which their data subjects give consent. For example, an organization might have individual checkboxes for notifications via text, email, fax, or phone on its consent form. These individual options are considered consent purposes.

In Securiti, you can create and assign a specific category to your processing purposes. For instance, if your processing purposes are inclined toward the marketing goals of your organization, you can create a Marketing category and assign it to all those processing purposes that fall under this category.

## Related

- [Using the Universal Consent Management Legacy Dashboard](/using-the-universal-consent-management-dashboard.md)
