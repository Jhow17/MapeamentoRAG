---
title: "Processing purpose categories"
slug: "processing-purpose-categories"
updated: 2025-10-30T19:44:33Z
published: 2025-11-03T06:12:47Z
canonical: "helpcenter.securiti.ai/processing-purpose-categories"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Processing purpose categories

You can build a library of processing purpose categories to use and map over your collected processing purposes. You can add a processing purpose category to your processing purposes while creating a new one or editing an existing processing purpose.

With processing purpose categories dashboard, you can:

- Add processing purposes category.
- Edit, clone, and delete existing processing purposes categories.
- View unique IDs in the ID column for each record.
- Add custom translations manually for multiple languages to translate processing purposes categories, and also remove them
- Filter out processing purposes categories from the dashboard by using a single property or combining multiple properties:
  - ID
  - Name
- Import and export translations in CSV format for mapping.
- Set pagination options to control the number of IDs per page view.

You can view the mapped *processing purpose* categories over the processing purposes in the processing purposes dashboard as shown below.

![Processing_Purpose_Categories_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-abbbb1cc-fc5a-1701-fd1d-fb778ee35dcd.png)

You can also view the processing purpose categories associated with consents directly from the Universal Consent dashboard. To view the processing purpose category associated with a specific consent, select any consent from the consent table in the main dashboard, and from the upper right corner of the dashboard, click the **Eye** icon as shown below.

![Processing_Purpose_Categories_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d519968-4c3b-b48e-dc37-492cb9ba4e9e.png)

You can also filter out consent records based on the associated processing purpose categories. To do so, use the **Processing Purpose Category** filter from the filters panel in the Universal Consent dashboard as shown below.

![Processing_Purpose_Categories_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-17c6e576-9895-f65d-8208-981adc0c0282.png)

### Using the top-level filter

The top-level filter lets you combine different properties of the Processing Purpose Categories and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. From the upper left corner of the Processing Purpose Categories dashboard, click **+**, as shown below.

![Processing_Purpose_Categories_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-282de133-bd11-2fcf-7028-8b39a21ad816.png)
2. On the popup, search for processing purposes categories by ID or name.

For instance, if you want to filter processing purpose categories by name (property), click **Name**, and from the right, type the name of the processing purpose and press **Enter**. Once done, near the bottom of the popup, click **Apply**, as shown below.

![Processing_Purpose_Categories_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f2a3d469-b63b-848d-2d1a-1020545c7daf.png)
3. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below.

![Processing_Purpose_Categories_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-af55f6bd-d257-b7ee-e204-ee1c6057cacd.png)
4. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![Processing_Purpose_Categories_7.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a82feca7-2c90-3f5d-14a4-5cefb9935024.png)

### Adding a processing purpose category

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent Configurations** **> Processing Purpose Categories**.
2. Near the upper right corner of the page, click **+ Add Processing Purpose Category** button or **+** icon as shown below.

![Processing_Purpose_Categories_8.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d81079e2-4c1f-556d-6b8b-384a736d2507.png)
3. On the **Add Processing Purpose Category** popup, enter a processing purpose category and description, as shown below.

![Processing_Purpose_Categories_9.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c9a245cf-f308-a025-ccfe-d6047b5a2c83.png)
4. Enable the **Enable Translation** toggle, select a language from the menu for which you want to provide custom translation against the processing purpose category, and click **Save** as shown below.

![Processing_Purpose_Categories_10.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8d29e306-a6dc-983c-b00a-b63f3df015ba.png)

### Processing Purpose category translation mapping

You can provide custom translations for your processing purpose categories while creating a new category or editing an existing one. To add a custom translation for your processing purpose category:

1. Create a new processing purpose category or edit an existing one by clicking **Options** (three dots) and then selecting **Edit**.
2. On the **Update Processing Purpose Category** popup, enable the **Enable Translation** toggle and select a language from the menu for which you want to provide custom translation against the processing purpose category as shown below.

![Processing_Purpose_Categories_11.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-020347ff-cc36-537a-14f1-28981f1f4872.png)

### Importing processing purpose category translations via CSV file

You can import translations for processing purpose categories via a CSV file. Translations from this CSV file are mapped over the processing purpose categories and their descriptions once you change the language from the menu of the **Add** or **Update Purpose Category** popup as shown below.

![Processing_Purpose_Categories_12.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9f719795-0a10-41a9-ab25-40a97bae4bc1.png)

To import the translations CSV file:

1. In Securiti, open **Universal Consent Management**, then choose **Universal Consent Configurations > Processing Purpose Categories**.
2. Click **+ Import Translations** on the top right side of the page.

![Processing_Purpose_Categories_13.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-02689613-d844-fbbf-37cd-cf6b6440ff25.png)
3. On the popup, click **Download CSV Template**, open the template and fill the CSV file cells with appropriate translations for your **Processing Purpose Categories** and their **Descriptions**.
4. Save the changes in your CSV file.
5. Either **drag and drop** the file or click **Select File to Import** to import the CSV file as shown below.

![Processing_Purpose_Categories_14.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-560688b7-aeba-2253-d5e2-3e9f0c3061c3.png)
6. Click **Import** to import your CSV file in the module.

### Exporting processing purpose category translations via CSV file

You can export the translations for the processing purpose categories via a CSV file. Clicking the **Export Translations** button on the purpose categories page downloads a CSV file in your device containing the translations for processing purpose categories.

![Processing_Purpose_Categories_15.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0694d592-7066-59e1-50bf-c77475ae25d9.png)

To export the translations CSV file:

1. In Securiti, open **Universal Consent Management** then choose **Universal Consent Configurations > Processing Purpose Categories**.
2. Click **Export Translations** on the top right side of the page.
3. This downloads a CSV file containing the translations for the processing purpose categories in your device.

## Related

- [Configuring processing purposes and consent purposes](/configuring-processing-purposes-and-consent-purposes.md)
