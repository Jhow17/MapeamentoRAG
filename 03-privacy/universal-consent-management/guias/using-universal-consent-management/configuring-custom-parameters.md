---
title: "Configuring custom parameters"
slug: "configuring-custom-parameters"
updated: 2026-03-31T10:54:25Z
published: 2026-03-31T10:54:25Z
canonical: "helpcenter.securiti.ai/configuring-custom-parameters"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring custom parameters

**Scenario**

As a Data Privacy Officer, you need consent records with enough context for audits and reporting, but standard fields may not capture business-specific details. For instance, when collecting consent for a marketing campaign, you may need attributes like campaign name, region, or channel. Without them, identifying relevant records becomes difficult. Custom Parameters let you add these details via Universal Consent APIs and filter them in the dashboard, helping you organize data, search faster, and gain more meaningful insights from consent records.

You can configure custom parameters to record consent and search consents from the pool of existing consents via the universal consent API. The main objective of creating custom parameters is that you can have the flexibility of having as many parameters for recording consent as you need. For instance, before [uploading consent](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#tag/Consent-Upload), you can associate it with custom parameters such as employee name and email. You can then use these parameters to filter the consent records directly from the dashboard.

With custom parameters dashboard, you can:

- Add custom parameters.
- Edit, clone, and delete existing custom parameters.
- Activate and deactivate existing custom parameters.
- View unique IDs in the ID column for each record.
- View detailed metadata for any custom parameters, as shown below.

![configuring_custom_parameters.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d784a888-e765-e625-3eb7-8b2684323f37.png)
- Filter out custom parameters from the dashboard by using a single property or combining multiple properties:
  - ID
  - Name
- Set pagination options to control the number of IDs per page view.

### Using the top-level filter

The top-level filter lets you combine different properties of the Custom Parameters and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Custom Parameters dashboard, click **+**, as shown below.

![top_level_filter_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-dbad9b72-9ba9-aac5-ce6b-3b15106f2e83.png)
2. On the popup, search custom parameters by ID or name.

For instance, if you want to filter custom parameters by name (property), click **Name**, and from the right, type the name of the custom parameters and press **Enter**. Once done, near the bottom of the popup, click **Apply**, as shown below.

![top_level_filter_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1c755409-0fcc-2877-c1b0-0add4c278bf0.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below.

![top_level_filter_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-551bc01e-93e7-fb8e-62de-05e5a56515d4.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![top_level_filter_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-31a9f5ab-7c82-7a0f-3fff-d443dc171643.png)

### Creating custom parameters

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Custom Parameters**.
2. Near the upper right corner of the page, click **+ Add Custom Parameters**.
3. On the **Add Custom Parameters** popup, enter the custom parameter name, its description and mark the **Active Status** checkbox as shown below, then click **Save**.

![creating_custom_parameter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6bce208a-3e53-b1cf-e431-8ce0fa9a2616.png)

> [!NOTE]
> **Note**
> 
> To activate the custom parameter upon creation, you must mark the **Active Status** checkbox.

### Deactivating custom parameters

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Custom Parameters**.
2. Click **Options** (three dots) on the right side of the record and then click **Deactivate** to deactivate the custom parameter as shown below.

> [!NOTE]
> **Note**
> 
> You can activate the deactivated custom parameter record by clicking **Options** again and then clicking **Activate**.

![1-deactivated_custom_parameter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-02105320-ad75-0c75-551a-93d4c1d101fc.png)![2-deactivated_custom_parameter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c96ceca9-835a-b845-c077-488613de17db.png)

### Editing custom parameters

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Custom Parameters**.
2. Click **Options** (three dots) on the right side of the record and then click **Edit** as shown below.
3. On the **Update Custom Parameters** popup, edit the custom parameter details and then click **Save**.

![editing_custom_parameter_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7dfea1c-ca41-64c1-9b91-927e8ea44c0b.png)![editing_custom_parameter_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f4dc26de-b3f1-f0ea-782e-05e4dbd19f3a.png)![editing_custom_parameter_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0407228c-aebe-6e5c-5e73-184eea7c7bc5.png)

### Deleting custom parameters

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Custom Parameters**.
2. Click **Options** (three dots) on the right side of the record and then click **Delete** to delete the custom parameter as shown below.

![deleting_custom_parameter_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e836615-59ac-2a12-7ed0-706e1ccb24b3.png)![deleting_custom_parameter_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7430b544-ad12-6afa-d1ed-874dcaaa6557.png)

## Related

- [Using the Universal Consent Management Legacy Dashboard](/using-the-universal-consent-management-dashboard.md)
- [Universal Consent Management API reference](/universal-consent-management-api-reference.md)
