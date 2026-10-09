---
title: "Configuring processing purposes and consent purposes"
slug: "configuring-processing-purposes-and-consent-purposes"
updated: 2026-03-31T11:31:22Z
published: 2026-03-31T11:31:22Z
canonical: "helpcenter.securiti.ai/configuring-processing-purposes-and-consent-purposes"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring processing purposes and consent purposes

**Scenario**

As a Data Privacy Officer, you must ensure that how your organization uses data matches what the data subject has agreed to. However, this becomes challenging when processing purposes and sub-processing (consent) purposes are not clearly linked. For instance, a data subject may agree to receive marketing emails, while their data is also used for internal analytics. If the link between processing and consent purposes is not clearly defined, you cannot demonstrate that data usage aligns with the consent provided. With Securiti's Processing Purpose and Consent Purpose, you can create and manage these purposes, link them appropriately, and ensure data usage aligns with consent while maintaining transparency and audit readiness.

You can build a library of processing purpose and consent purpose to use when you collect consent on website forms as described in [Collecting form consent](/v1/docs/collecting-form-consent).

- Processing Purposes are the purposes for which you are processing a data subject's personal data. You can have one processing purpose for each form.
- Consent Purposes are more granular; they are purposes for individual things to which the data subject consents. For example, if your form has checkboxes for notifications via text, email, or phone, you would create a consent purpose for each of those notification types.

For more information on how to add consent records with multiple data subject identifiers, see [Multiple Data Subject Identifiers for consent records](/v1/docs/multiple-data-subject-identifiers-for-consent-records).

With processing purposes and consent purposes dashboard, you can:

- Add processing purposes and consent purposes.
- Edit, clone, and delete existing processing purposes and consent purposes.
- View unique IDs in the ID column for each record.
- Add custom translations manually for multiple languages to translate processing purposes and consent purposes, and also remove them.
- Import and export translations in CSV format for mapping.
- View detailed metadata for any processing purpose or consent purpose, as shown below.

![Overview of processing purposes including service provision and associated details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_1.png)
- Filter out processing purposes and consent purposes from the dashboard by using a single property or combining multiple properties:
  - ID
  - Name
  - Category
- Set pagination options to control the number of IDs per page view.

### Using the top-level filter

The top-level filter lets you combine different properties of the Processing Purpose and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Processing Purpose dashboard, click **+**, as shown below.

![Overview of processing purposes with associated categories and external IDs listed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_2.png)
2. On the popup, search for processing purposes by ID, name, or category.

For instance, if you want to filter processing purposes by category (property), click **Category**, and from the available list on the right, mark the radio button next to the categories you want to filter by. Once selected, near the bottom of the popup, click **Apply**, as shown below.

![Dropdown menu showing categories for processing purposes, including educational and marketing options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_3.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below.

![Overview of processing purposes with details on service provision and associated categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_4.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![Filters for processing purposes include ID, Name, External ID, and Category criteria.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_5.png)

### Adding a processing purpose

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Processing Purposes**.
2. Near the upper right corner of the page, click **+ Add Processing Purpose**.
3. On the Add Processing Purpose popup, enter a purpose and description as shown below, then click **Save**.

![Form for adding processing purposes with highlighted email marketing section and description.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_6.png)

> [!NOTE]
> Note
> 
> The **External ID** field is optional. It can be used to record consents associated with a processing purpose, but it is not required for the creation or use of that processing purpose.

### Importing processing purpose translations via CSV file

You can import translations for processing purposes via a CSV file. Translations from this CSV file are mapped over the processing purposes and their descriptions once you change the language from the menu of the Processing Purpose popup, as shown below.

![Form for adding processing purposes with translation options and categories displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_7.png)

To import the translations CSV file:

1. In Securiti, open **Universal Consent Management**, then choose **Universal Consent Configurations > Processing Purposes**.
2. Click **+ Import Translations** on the top right side of the page, as shown below.

![Overview of processing purposes with associated categories and external IDs for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_8.png)
3. On the popup, click **Download CSV Template**, open the template and fill the CSV file cells with appropriate translations for your **Processing Purposes** and their **Descriptions**.
4. Save the changes in your CSV file.
5. Either **drag and drop** the file or click **Select File to Import** to import the CSV file, as shown below.

![Interface for importing translations via CSV with highlighted drag-and-drop area.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_9.png)
6. Click **Import** to import your CSV file in the module.

### Exporting consent and processing purpose translations via CSV file

You can export the translations for the consent and processing purposes via a CSV file. Clicking the **Export Translations** button on the processing or consent purpose page downloads a CSV file in your device containing the translations for processing purposes or consent purposes.

To export the processing purposes translations CSV file:

1. In Securiti, open **Universal Consent Management**, then choose **Universal Consent Configurations > Processing Purposes**.
2. Click **Export Translations** on the top right side of the page.
3. This downloads a CSV file in your device containing the translations for the processing purposes, as shown below.

![Overview of processing purposes with details on service provision and marketing categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_10(1).png)

To export the consent purposes translations CSV file:

1. In Securiti, open **Universal Consent Management**, then choose **Universal Consent Configurations > Consent Purposes**.
2. Click **Export Translations** on the top right side of the page.
3. This downloads a CSV file in your device containing the translations for the consent purposes, as shown below.

![Overview of consent purposes with associated IDs and export options for translations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_11(1).png)

### Using the top-level filter

The top-level filter lets you combine different properties of the Consent Purpose and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Consent Purpose dashboard, click **+**, as shown below.

![Overview of consent purposes with options to filter and manage data processing actions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_12.png)
2. On the popup, search for consent purposes by ID or name.

For instance, if you want to filter consent purposes by name (property), click **Name**, and from the right, type the name of the consent purpose and press **Enter**. Once done, near the bottom of the popup, click **Apply**, as shown below.

![User interface for managing consent purposes with filters and associated forms displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_13.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below.

![Consent management interface displaying marketing purpose with ID and external ID details.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_14.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![User interface for managing consent purposes with filters and options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_15.png)

![Consent_Purpose_Filter_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-139a2dba-4009-f226-dfba-d0caf2026b36.png)

### Adding a consent purpose

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations > Consent Purposes**.
2. Near the upper right corner of the page, click **+ Add Consent Purpose**.
3. On the **Add Consent Purpose** popup, enter a consent purpose as shown below, then click **Save**.

![Adding a new consent purpose for email marketing in the management portal interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_16.png)

> [!NOTE]
> Note
> 
> The **External ID** field is optional. It can be used to record consents associated with a consent purpose, but it is not required for the creation or use of that consent purpose.
4. Enable the **Enable Translation** toggle, select a language from the menu for which you want to provide custom translation against the consent purpose, and click **Save** as shown below.

![Adding a consent purpose for email marketing with translation options available.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/PPCP_17.png)

## Related

- [Collecting form consent](/collecting-form-consent.md)
- [Building a universal preference center](/building-a-universal-preference-center.md)
