---
title: "Importing and exporting data mapping items"
slug: "importing-and-exporting-data-mapping-items"
updated: 2025-12-09T07:32:04Z
published: 2025-12-09T07:32:04Z
canonical: "helpcenter.securiti.ai/importing-and-exporting-data-mapping-items"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Importing and exporting data mapping items

You can import all data mapping item types (assets, vendors, etc.) from .csv files, and also export assets, vendors, and institutions to .csv files.

When importing, you don’t need a template for the CSV file; you identify the columns during the import operation.

> [!NOTE]
> **Note**
> 
> Observe the following caveats for the .csv file:
> 
> - The first row is assumed to contain the column names.
> - Where a column contains a list of items (for example for a reference list [multiple]), separate the items with semicolons instead of commas.
> - Where a column contains a range, for example "0-500", use only a standard hyphen "-" to separate the values. Do not use the em-dash that you get when type option-shift-hyphen, and make sure your spreadsheet editor hasn't autocorrected hyphens to em-dashes.
> - You can also import lists of data element types with the entities. In the CSV file, separate the data element types as shown here:
> 
> ```plaintext
> Name, data_element_types
> b1,CASE_ID
> b3,CASE_ID;DEVICE_ID;DEVICE_TYPE
> b6,API_KEY;ID;ADVERTISING_IDENTIFIER
> ```
> 
> Use the Data Element Types field to identify the data element types as shown below.
> 
> ![RN_import_data_element_types.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4d76eb43-169f-f2b4-4a1e-17d427c379d2.png)
> - It is worth noting that any assets you create via a CSV import are unmonitored assets.

### Importing data mapping items from a .csv file

You can import any data mapping item types from .csv files.

1. In Securiti, open **Data Mapping Automation**, click **Catalog**, and choose the type of catalog item you want to import.
2. On the page for that catalog item type, near the upper right corner of the page click **Import via CSV**.
3. On the Import via CSV popup, navigate to the .csv file or drag the file into the drag & drop box.
4. Choose the data mapping template for the elements you want to import, and click **Import** as shown below.

![Screenshot_2024-05-21_at_4_49_50_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9a56c5ef-1741-6b51-0973-858585216ebe.png)

![Screenshot_2024-05-21_at_4_51_52_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7446bc3-6a46-0cf9-6879-d6d6c8db9037.png)
5. On the Map CSV Fields to Asset Fields page, drag the available fields from the right side onto the fields found in the CSV file on the left side as shown below.

![Screenshot_2025-04-28_at_4_12_22_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-91ed5084-a5af-8548-ad77-367b6e6e7839.png)

The **Key-off** option lets you manage unique assets via bulk upload. Whichever field is set as key-off, Securiti runs a check to ensure data is updated if it exists in DB and create it if it doesn’t exist, and refrains from creating duplicate data for the same asset.

Also, you can apply key-off feature to only specific type of fields because different organizations have different IDs, and the key-off feature enables you to identify that. By default, Securiti considers the name as key-off.

> [!NOTE]
> **Note**
> 
> If you have previously imported devices from CSV files and saved the mappings between the CSV fields and the Securiti entity fields, you can click **Load Existing Mapping** to apply that mapping to the current import operation. To delete mappings that are no longer applicable, click **Delete Mappings** to delete those saved mappings.
6. (Optional) To save the mapping so you can use it in the future with other files of the same format, click **Save Mapping As** and use the Save Mapping popup to give the mapping a name.
7. When you are done, click **Import**.
8. Securiti processes the import and sends you a notification when it is done.

### Exporting data mapping items to .csv files

You can export assets, vendors, and institutions to CSV files. If you have filtered the page so that only certain items appear, only those items are listed in the CSV.

1. In Securiti, open **Data Mapping Automation**, click **Catalog**, and choose the type of catalog item you want to export.
2. Near the upper right corner of the page, click **Export as CSV**.

Securiti schedules the export, and emails you with a link when the .csv file is ready to download.
3. Click the link in the email to download the .csv file.

An asset records data for any application or store. You can use It to record an asset's name, description, purpose, etc. Also, you can use an asset in processes.

## Related

- [Creating custom assessment templates in Securiti](/creating-custom-assessment-templates-in-securiti.md)
- [Creating and customizing Data Mapping Automation reference lists](/creating-and-customizing-data-mapping-automation-reference-lists.md)
