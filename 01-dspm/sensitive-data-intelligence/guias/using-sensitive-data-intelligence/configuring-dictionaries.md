---
title: "Configuring dictionaries"
slug: "configuring-dictionaries"
updated: 2026-04-27T10:36:07Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/configuring-dictionaries"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring dictionaries

You can configure dictionaries for the classification of unstructured data files according to keywords that occur within them. Securiti comes with several system dictionaries. You cannot edit or view the contents of these proprietary dictionaries, but you can add additional dictionaries of your own.

> [!CAUTION]
> Warning
> 
> The character limit for naming classification resources and their categories is 50 characters. If a name exceeds this limit,​ Securiti shows an error message. Existing names remain unchanged.

You do not have to enable or disable individual dictionaries; instead, you can reference them in the **Definitions** section when you configure data element types, as shown below.

![dictionariesinDataElements.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-640178ed-50e4-2bf4-b093-6b3ea69f1e65.png)

You can also search the system dictionaries for specific keywords to make sure that they address your needs.

### Searching for a keyword

- Use the search box near the upper right corner of the page, as shown below.

![Search bar for dictionaries with categories and total dictionaries displayed on the screen.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.26.46 PM.png)

### Searching a dictionary

To create a new custom dictionary:

- Open the Securiti **Sensitive Data Intelligence** module and from the left panel, choose **Data Classification > Dictionaries**. Use the search box near the upper right corner of the page, as shown below.

### Creating a custom dictionary

To create a new custom dictionary:

1. From the main menu, choose Sensitive Data Intelligence > Data Classification > **Dictionaries**.

![Securiti interface displaying Sensitive Data Intelligence and Data Classification options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.26.37 PM.png)
2. On the **Dictionaries** page, near the upper right corner of the page, click **+ New Custom Dictionary**.
3. Enter the name of your dictionary.
4. To add a new custom dictionary category or to move it to another category, click **Add New**. Enter the name of the custom category and press **ENTER** or **RETURN** key. To move it to a new category, choose the one you added.

> [!NOTE]
> **Note**
> 
> - The custom dictionary that you create belongs to the specific organization in which you create it.
> - You can create a custom dictionary up to a limit of 200 keywords.
5. Select a language for your dictionary.
6. As a first option, you can add a list of keywords to be included in your dictionary.

![dictKeywords.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3a624742-ba5d-feb9-4b6c-7250915aea00.png)
7. Alternatively, you can create a `CSV` file (with `.CSV` extension), add keywords and phrases separated by new lines to include in the dictionary, and click **Import File** to upload the file.

![customDictCSV.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-768835b7-2080-3cae-4419-2c18bbe7b88a.png)
8. If the dictionary items are not case-sensitive, choose **No**.

![dictCaseSensitive.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9c1bbace-3a6a-a1cd-e951-1a363fb06dbc.png)
9. When you are done, click **Save Dictionary**.

### Renaming a custom dictionary

Once you add a custom dictionary, from an entry, click Options (three dots) to rename that category and press **ENTER** or **RETURN** key. The changes to these custom categories are reflected under the discovery scan results and structured and unstructured data explorers.

> [!NOTE]
> **Note**
> 
> You can only rename the title of the custom dictionary category; you cannot rename the system categories.

## Related

- [Configuring custom data element types](/configuring-custom-data-element-types.md)
