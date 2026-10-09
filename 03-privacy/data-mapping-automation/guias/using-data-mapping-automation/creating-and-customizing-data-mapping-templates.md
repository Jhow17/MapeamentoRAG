---
title: "Creating and customizing data mapping templates"
slug: "creating-and-customizing-data-mapping-templates"
updated: 2025-12-09T08:23:38Z
published: 2025-12-09T08:23:38Z
canonical: "helpcenter.securiti.ai/creating-and-customizing-data-mapping-templates"
area: privacy
modulo: data-mapping-automation
tipo: guia
data_captura: 2026-10-08
---

# Creating and customizing data mapping templates

**Scenario**

As a Data Compliance Officer working with the IT team, you need your data catalog to reflect internal policies. Standard definitions and workflows don’t always match how your organization classifies or handles data. By customizing catalog terms and approval paths, you align governance practices with internal standards. This ensures consistent data handling across teams and supports policy enforcement at scale.

#### Creating and customizing data mapping templates

Data mapping definition templates control what information you collect for the various catalog items (asset, vendor, etc.) when adding or editing them in your data mapping. Each template has one or more sections dedicated to the different types of information you collect and process.

Securiti come with several pre-defined system templates, that you can edit but not delete. You can also create custom templates by cloning and editing system templates.

### Opening a template for editing, or cloning or deleting a template

To open a template for editing, or to clone or delete a template:

1. In Securiti, choose **Data Mapping > Settings >** Definitions.
2. On the Catalog Definitions page, in the Templates panel, do one of the following:

> [!NOTE]
> **Note**
> 
> Post implementation of the Object and Field question types in Securiti, you can no longer delete the catalog definitions.
> 
> For more information, see [Object Field Framework](/v1/docs/creating-custom-assessment-templates-in-securiti).
  - Click a template to open it for editing.
  - Next to the template, choose **Options** (three dots)**> Clone**.

### Editing a template

To edit a template:

1. Open the template for editing as described above.
2. In Securiti, open Data Mapping Automation and choose **Settings > Definitions**.
3. In the Templates panel, click the template you want to edit.
4. In the main panel, expand the various sections and configure their contents as follows:

![Screenshot_2025-04-29_at_11_27_21_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55bbbafa-37bd-bb22-f186-4edb1852e92c.png)

> [!NOTE]
> **Note**
> 
> If you change the input type for an existing field, Securiti alerts you that you will lose any information that you have previously collected in this field, as shown below. If you are editing a newly-cloned template that you have not yet used to create any data mapping items, you can safely disregard this alert.
> 
> ![Screenshot_2025-04-29_at_12_22_45_PM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d2221610-e102-96b5-c2bd-dd574ff3938e.png)
  - To restrict access to the section so that only certain types of users can view or edit it, click **Restrict Access** and use the Restrict Access popup to set which user types can view or edit the section. See [Restricting access to catalog item sections](/v1/docs/restricting-access-to-catalog-item-sections) for more information.
  - To enable or disable a field, toggle its slider.
  - To add a new field, click **Add New Field** at the bottom of the section.
  - To add a Reference List to a field, for Input Type, choose one of the following reference list types, then choose the reference list. See [Creating and customizing Data Mapping Automation reference lists](/v1/docs/creating-and-customizing-data-mapping-automation-reference-lists) for more information:
    - Reference List (Single) lets you choose only one item from the list.
    - Reference List (Multiple) lets you choose multiple items from the list.
  - To hide a section, enable its **Hide Section** slider.

> [!NOTE]
> **Note**
> 
> You can hide any section except Data Store Information.
  - To add a new section, click **Add New Section** at the bottom of the list of sections.
5. Near the upper right corner of the page, click **Save**.

> [!NOTE]
> **Note**
> 
> You can edit the text fields for new assessment templates only but not for the existing templates.

### Importing a template

To import an existing template:

1. Near the upper right corner of the page, click **Import Definition**.
2. On the **Upload** popup, drag and drop or select a JSON file similar to a sample structure below.

![Screenshot_2025-04-29_at_11_24_20_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3840fe29-8f2d-6484-3034-39c48a635f6f.png)

```json
{
  "label": "Function/Purpose",
  "help_text": "Function/Purpose",
  "input_type": "TEXT",
  "metadata": {
    "type": "PURPOSE"
  },
  "is_enabled": true,
  "is_internal": true,
  "is_hidden": false,
  "is_fixed": true,
  "position": 1
}
```
3. Click **Upload**

![Screenshot_2025-04-29_at_11_25_38_AM.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86d57aac-53cf-be67-e247-81adbdad8ff0.png)

Securiti shows you the imported template in in the left sidebar under Templates.

Catalog Definitions define what sections and fields an entity uses to record the details.

An Object or an Object Question is an entity that holds data and is part of the Assessment V2 Object and Field Framework. For example, a Data Mapping entity such as an Asset or a Process is an Object. This can also mean any entity in the source of truth module and not limited to Data Mapping is considered an Object that you can use to create object questions in the assessment.

A Field or Field Question defines the Object that holds the data and is part of the Assessment V2 Object and Field Framework. For example, a Field Question(s) for a Data Mapping entity such as an Asset may expand on its Purpose, Description, Data Store Information, or Host Type. Similarly, a Field (Process) Question(s) can map the organizational structure or the legal basis for that process.

This can also mean that a field question defines any entity in the source of truth module, including Data Mapping, and can be linked to existing or new objects.

A reference list is a set of options or settings that lets you configure questions in a risk assessment, such as Single or Multi-select.
