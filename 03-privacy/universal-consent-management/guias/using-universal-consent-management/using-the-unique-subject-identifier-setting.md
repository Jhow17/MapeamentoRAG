---
title: "Using the Unique Subject Identifier setting"
slug: "using-the-unique-subject-identifier-setting"
updated: 2026-04-02T07:55:31Z
published: 2026-04-02T07:55:31Z
canonical: "helpcenter.securiti.ai/using-the-unique-subject-identifier-setting"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Unique Subject Identifier setting

**Scenario**

As a Data Privacy Officer, you must ensure that consent records are consistently linked to the correct identifiers across systems. However, when different teams use identifiers such as Customer ID, Device ID, or Email Hash to track consent, it becomes difficult to know which UUIDs are active and how many are being used across organizations. For instance, your marketing platform may store consent using a Customer ID while your mobile app relies on a Device ID, making visibility and governance challenging. Securiti’s Unique Subject Identifiers lets you create and manage identifiers that uniquely represent each data subject, helping you consistently track and locate their consent records.

The Unique Subject Identifier (UUID) setting lets you streamline consent tracking by maintaining a catalog of all UUIDs per organization in one place. It lists your UUIDs for easy access and helps determine the number of UUIDs you are using per organization in your Securiti tenant.

Securiti provides two out-of-the-box system UUIDs:

- email
- uuid

You can create and edit custom UUIDs as needed. Additionally, you can clone both system and custom UUIDs to different organizations within your Securiti tenant for seamless data management.

> [!NOTE]
> **Note**
> 
> - Only the following Securiti user roles in your organization have permission to create, read, and update UUIDs, while all others have READ permissions:
>   - Super Admin
>   - Org Admin
>   - Module Owner
> - Securiti logs all changes made to the UUID settings in the platform Audit log.

![UUID_list_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c0a4aab0-dbdf-1dc4-5bec-ee597269873e.png)

For new customers:

- Securiti lets you create up to 10 custom UUIDs per organization within your Securiti tenant.
- You must register UUIDs in the admin portal before uploading consent records via consent upload APIs.
- You must only use registered and unique UUIDs in API payloads because Securiti rejects payloads with unregistered or non-unique UUIDs.

For existing customers:

- Securiti lets you create up to 10 custom UUIDs per organization within your Securiti tenant.
- With Securiti release 1.129, Securiti automatically extracts your existing non-registered UUIDs used for consent uploads or retrieval via the admin portal or consent APIs and populates them on the Unique Subject Identifiers list page.
- Securiti lets you create more UUIDs from web-based consent forms, preference centers, and consent APIs, and populates them on the Unique Subject Identifier list page.

For instance, if you already have 10 UUIDs registered on the admin portal, and request consent payload via API using a new unregistered UUID, Securiti automatically creates that UUID in the Unique Subject Identifier list page in the admin portal instead of rejecting the API request.

> [!WARNING]
> **Warning**
> 
> Securiti will start rejecting API payloads with unregistered UUIDs for existing customers in future releases.

### Key Considerations

Use the following table to understand how to use UUIDs when uploading consent records:

| Criteria | Description |
| --- | --- |
| Creating a UUID | Securiti does not let you create duplicate UUIDs, and strongly recommends that each UUID associated with a data subject must be unique. For instance, if an `email_address` UUID already exists, you cannot create another UUID with the same name. However, you can create a UUID with a different name, such as `email`. |
| Editing a UUID | You can edit only the Custom UUID name but cannot change the data type. For instance, if a UUID is named `name`, you can rename it to `first_name`, but its data type (such as `Text` or `Numeric`) remains the same. |
| Deleting a UUID | Securiti does not let you delete a UUID after you create it. |
| Validating a UUID | Securiti rejects consent upload requests using UUIDs from the following sources if those UUIDs are not registered in the admin portal: - Form - Preference Center - Universal Consent APIs: - [Single consent upload](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Consent%20upload) - [Bulk consents upload](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Bulk_import_consents) - [Bulk consents upload in CSV file format](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Bulk_import_consents_via_csv) - [Read user latest consent status](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Fetch_the_latest_consent_status_of_data_subjects) - [Purpose preference center link external](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/pf_direct_path) - Bulk consent uploads via the admin portal using JSON and CSV file formats - Consent narrow path (Selective consent management) |

With the Unique Subject Identifier setting, you can:

- Create up to 10 new Custom UUIDs.
- Edit the name and description of Custom UUIDs.
- Clone both System and Custom UUIDs to different organizations within your Securiti tenant.
- Filter out the existing UUIDs from the dashboard by using a single property or combining multiple properties:
  - Name
  - Data Type such as Text or Numeric
  - Type such as Custom or System

### Using the top-level filter

The top-level filter lets you combine different properties of the UUIDs and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Unique Subject Identifier dashboard, click **+**, as shown below

![UUID_filters1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ff6dccc7-a187-7b6b-c6ea-f6dba09c6d43.png)
2. On the popup, search by UUID name, data type, or UUID type, either custom or out-of-the-box system.

For instance, if you want to filter UUIDs by data type (property), click **Data Type**, and from the available list on the right, mark the radio button next to the data type you want to filter by. Once selected, near the bottom of the popup, click **Apply**, as shown below.

![filter_UUID_dataype.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1ceaec8c-285a-756b-9634-3f29fad9ad6e.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below.

![UUID_filters_by_multiple_properties.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e5fd18c-49a1-c288-9985-f07eab48c2ab.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![Clear_search.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a5f5bdc-1031-5faa-52c9-fa6cdffc6e67.png)

### Creating a new Custom UUID

On the Unique Subject Identifier list page, you can create custom UUIDs, which must be unique, and Securiti does not let you delete them after creation.

To create a new custom UUID:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Unique Subject Identifiers**.
2. On the Unique Subject Identifier list page, from the upper right corner, click **+ New Unique Subject Identifier**, as shown below.

![Create_UUID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-af16fac7-2c26-917e-6324-1e8af680cbca.png)
3. On the **New Unique Subject Identifier** popup, fill out details for:

| Fields | Description |
| --- | --- |
| Unique Subject Identifier Name | Enter a unique name for the UUID you are registering on the Unique Subject Identifiers list page. > [!NOTE] > **Important** > > The **Unique Subject Identifier Name** field is case-sensitive. For instance, Securiti considers `PHONE` and `phone` as different UUIDs. |
| Data Type | From the menu, choose the type of UUID, such as **Text**, or **Numeric**. |
| Description | Enter a description for the UUID to provide context or additional details. |
4. Near the bottom of the popup, click **Create**, as shown below.

![Create_UUID2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fafca3b7-3fc1-a92f-d056-3a4b8ae87088.png)

Securiti creates the UUID and shows a success message near the upper-right corner of the screen.

### Editing Custom UUIDs

Securiti lets you modify the name and description of UUIDs. You can rename a UUID only to a similar data type.

> [!NOTE]
> **Note**
> 
> You can rename a Unique Subject Identifier (UUID) to a similar data type only. For example, if it is named `email`, it can be changed to `email ID` or `email address`, but not `phone number`.

To edit a Custom UUIDs:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Unique Subject Identifiers**.
2. From the right side of the UUID you want to edit, click **Options** (three dots) and select **Edit**, as shown below.

![Edit_UUID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a2f0e60a-731b-4865-b536-9453a8faab66.png)
3. On the **Edit Unique Subject Identifier** popup, modify the fields you want to update such as UUID name or description. Once you are satisfied with the changes, near the bottom of the popup, click **Update** to save your changes, as shown below.

![Edit_UUID2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f5a0901b-cbdc-fc02-0249-9b21ba766b1e.png)

Securiti updates the UUID and shows a success message near the upper-right corner of the screen.

### Cloning System and Custom UUIDs

Securiti lets you clone system and custom UUIDs across organizations within your Securiti tenant.

To clone UUIDs:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Unique Subject Identifiers**.
2. From the right side of the UUID you want to edit either System or Custom, click **Options** (three dots) and select **Clone**, as shown below.

![Clone_UUID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4bbf9cf3-ca48-2a36-5606-03b05902cfc1.png)
3. On the **Clone Unique Subject Identifier** popup, select the organization to which you want to clone UUID from the **Select Organization** menu, as shown below.

![Clone_select_org.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-083f79e4-8bde-c123-bd7e-5a56f5ba9b1b.png)
4. Once you select an organization, click **Clone**, as shown below.

![Clone_UUID3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-515c96c0-b5b4-01d9-c304-1be658caf2a2.png)

Securiti clones the UUID, and shows a success message near the upper-right corner of the screen.

The log that Securiti maintains of all actions taken by various users, and by the Securiti system. Different users have different levels of access to the audit log. For users of type Super Admin, DPO, and Operator, the audit log shows all log entries. For users of type User or Module Owner, the audit log only shows log entries directly related to the user and their activities.

## Related

- [Using the Universal Consent Management Legacy Dashboard](/using-the-universal-consent-management-dashboard.md)
- [External UUID linking for consent records](/external-uuid-linking-for-consent-records.md)
