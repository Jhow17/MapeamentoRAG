---
title: "Structured properties"
slug: "structured-properties"
updated: 2026-07-19T19:39:57Z
published: 2026-07-19T19:39:57Z
canonical: "helpcenter.securiti.ai/structured-properties"
stale: true
area: governance
modulo: enterprise-data-catalog
tipo: guia
data_captura: 2026-10-08
---

# Structured properties

**Scenario**

As a data steward, you are responsible for maintaining consistent metadata across thousands of catalog entries. With free-form key/value pairs, you often run into typos, inconsistent formats, and governance headaches. Using structured properties, you define controlled formats and allowed values for each attribute. This improves data quality, enforces consistency, and reflects your organization’s specific governance standards.

Structured properties are a powerful way to customize your EDC environment, enabling you to align metadata with your organization’s unique needs. By defining specific property types—such as date, number, string, or URN—you can apply meaningful, context-aware attributes to your EDC assets. Validation rules, like restricting allowed values or enforcing specific formats, ensure consistency while giving you the flexibility to reflect your business’s terminology, workflows, and priorities.

### Why use structured properties?

EDC currently lets you create custom properties that can be added to assets through key/value pairs, offering flexibility for contributors to add additional context. However, this approach has challenges in governance, as user-defined key/value pairs often lead to data entry errors. You might misspell keys or values, and some properties may only allow specific values. Structured properties address these issues by offering a more reliable and consistent way to define and manage attributes.

### Prerequisites

To perform actions on Structured Properties, enable the **Manage Structured Properties** permission for your account. For more information, see [EDC RBAC](/latest/docs/edc-rbac-permissions-and-roles).

### Scope of structured properties

Currently, structured properties can be added to the following EDC entities:

- Dataset
- Container
- Domain
- Glossary term
- Glossary node
- Data product

### Accessing structured properties

To access structured properties:

- Open **Enterprise Data Catalog**, and navigate to **Settings > Structured Properties**.

![Structured_properties_-_Opening_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ac1d41b9-68fb-5261-c1aa-d2c881beb207.png)

### Structured properties dashboard

This page lets you create and manage structured properties.

![Screenshot_2025-05-29_at_4_51_57_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73ba1294-73f1-8ae8-dd61-5786ccc0ceba.png)

- At the top, the dashboard shows you the search bar to search created properties by their names.

To further filter the structured properties, you can use the following filters located below the search bar:

| Filter | Description |
| --- | --- |
| Value type | This menu lets you filter structured properties by their names. 1. Click the down arrow. 2. Select the operator. 3. Enter the value in the search menu and choose from the listed options. 4. Click **Apply** to see the filtered results. |
| Owner | This menu lets you filter properties by their owners. 1. Click the down arrow. 2. Select the operator. 3. Enter user details in the search bar and choose from the listed options. 4. Click **Apply** to see the filtered results. |

- Below the filter menus, you can view the count of created structured properties.

### Exploring structured properties

Below the filtering options, the table presents a list of created structured properties.

For each created structured property, you can view the following details:

- Status

> [!NOTE]
> **Note**
> 
> By default, the status is set to inactive. After creating the structured properties, you must activate the status to link them to the EDC entities.
- Property name

Click the copy icon at the end of the property name to copy its URN. You can use this URN anywhere in the Data Catalog.
- Fully qualified name

It represents a unique identifier for each structured property in the EDC. It is a structured naming convention that ensures clarity and uniqueness across different properties within the system. The copy icon next to the **Fully Qualified Name** lets you quickly copy this unique identifier, making it easier to search for and reference the structured property within the system.
- Value type
- Total values

Total number of values created against one structured property.
- Property owner

> [!NOTE]
> **Note**
> 
> On the right side of the owner column, you can find the column selector. It lets you choose which columns to display in the tables listing structured properties. This way, you can customize the view according to your preferences. You can also reset the selection to default settings.

You can display the following columns in the table listing structured properties:

- Status
- Property name
- Value type
- Total values
- Owner

- Click **Metadata Explorer** icon located to the right of the property owner to explore the detailed information.

### Creating structured properties

To create a structured property:

1. On the structured property dashboard, at the top right corner of the page, click **Create Property**.
2. On the creation pop-up, configure the following details:
  1. In the **Property Information** section, enter a unique name and brief description of the property.
  2. In the **Value Settings** section, configure:
    1. The types of values from the **Value Type** menu. The available value types are as follows:

| Value type | Description |
| --- | --- |
| Number | This value type is used for numerical data. It can represent integers or decimals. Numbers are ideal for quantitative attributes like counts, measurements, or any data that needs mathematical operations. |
| Date | This value type is used to store date-related information. It can represent a specific date or a date-time combination. Dates are commonly used for tracking timelines, deadlines, or any temporal data in the system. |
| String | This value type is used for alphanumeric data, including text and characters. It is ideal for any attribute that involves descriptive information, such as names, titles, descriptions, or other free-form data that doesn't fit into numeric or date categories. |
| URN | This value type is used for URNs, which are identifiers that uniquely represent a resource. URNs are typically used for referencing resources in a globally unique way, often used in situations where identifiers need to be persistent over time. |
    2. Once you have selected any value type, then under the **Allowed Values** section, enter possible values.

> [!NOTE]
> **Note**
> 
> You can delete any added values before saving the structured property. Once the structured property is created, you can no longer edit or delete the added values. To delete the value:
> 
> - Click **Options (three dots) > Delete**.
      1. Click **+ Add Value**.
      2. Enter a value in the **Value** field. For example, if the value type is **Number**, you might enter **45.67**, which is a decimal number.
      3. Provide a description in the **Description** field. For the value 45.67, an appropriate description could be: "A decimal value, useful for representing measurements, percentages, or any data requiring precision."
      4. Click the tick icon to save the property value.
  3. Under the **Cardinality** section, select either **Single** or **Multiple**. If you select **Single**, only one value of the structured property can be assigned to the entities. If you select **Multiple**, you can assign multiple values to the entities.
  4. In the **Entity** **Selection** section, click the **+** button next to the **Select Entities** field to open the entity types.
    1. From the list of entity types, select the entity and then choose the relevant instances. Alternatively, to apply the configuration to all instances at once, simply check the **Select All** checkbox at the top of the instances list, without selecting individual instances.
    2. Click **Apply**.

> [!NOTE]
> **Note**
> 
> You can select multiple entities simultaneously and apply the structured property across all selected entities.
  5. Click **Create Properties**.

![Screenshot_2025-05-29_at_4_55_07_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6d50ca4-8709-e60b-ace7-1a3ddee8c6ca.png)

Once created, the structured property is immediately displayed in the list on the structured property dashboard.

### Linking structured properties to EDC entities

Once your structured property is created and enabled from the structured properties dashboard, you can view it in the relevant entity. To view the linked structured property:

1. In the **Enterprise Data Catalog**, open the entity for which the structured property has been created.
2. Open the **Properties** tab to view all properties, including both structured and custom properties.

By default, the structured property is linked to the entity; however, the possible values are not automatically assigned to the property. You will need to manually select the values for the property.

> [!NOTE]
> **Note**
> 
> If you edit a structured property with values from the Edit Property page and the property is already assigned to an entity, the new values will not be automatically reflected. To update them, you need to click the edit icon again and manually attach the new values to the property.

### Configuring values for structured property within an entity

#### Adding values to the structured property within an entity

To add a value to the structured property within the entity:

1. Click the edit icon located at the right end where the structured property is presented under the **Properties** tab.
2. In the pop-up, select the values from the list. If the cardinality is set to **Multiple** during the creation of the structured property, you can select multiple values. If the cardinality is set to **Single**, only one value can be selected.
3. Click **Update** to successfully set the value to the structured property.

![Screenshot_2025-05-29_at_5_01_10_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e630a3fd-9b63-34e1-2f9e-078066ac2eeb.png)

#### Editing structured property values within an entity

Setting a value for the structured property does not mean it’s permanent or unchangeable. You can update the values whenever needed. To edit a value:

1. Click the edit icon located at the right end where the structured property is presented under the **Properties** tab.
2. In the pop-up, select the values from the list to update.
3. Click **Update**.

#### Resetting structured property values within an entity

To reset the value to none:

- Click the reset icon located to the left of the edit icon.

### Searching for a structured property

Once you have assigned a value to a structured property on a dataset, you can easily search for it using the EDC main search bar. Use the following format to search for a structured property:

**/q structuredProperties.DataQualityScore:val1**

- **/q structuredProperties.**: This is a constant prefix required for all structured property searches.
- **DataQualityScore**: This is the fully qualified name of the structured property, which you can copy from the Structured Properties list in the dashboard.
- **:val1**: This is the value you want to search for within the specified structured property.

### Editing a structured property

To edit a structured property:

1. On the structured property dashboard, click **Options (three dots) > Edit Property**.
2. On the structured property popup, you can edit all the details of the structured property:
  - Property name
  - Property description
  - Value type
  - Allowed values
  - Cardinality
  - Entities
  - Entity instances

### Deleting a structured property

To delete a structured property:

1. On the structured property dashboard, click **Options (three dots) > Delete Property**.
2. On the delete property pop-up, click **Delete Property**.

An entity is a specific and distinguishable object in the Enterprise Data Catalog. It could represent various things like datasets or glossary terms.

## Related

- [Datasets](/datasets.md)
- [Domains](/domains.md)
- [Glossary terms](/glossary-terms.md)
- [Data products](/data-products.md)
