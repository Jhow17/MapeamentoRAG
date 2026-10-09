---
title: "Configuring content profiles"
slug: "configuring-content-profiles"
updated: 2026-04-06T16:51:05Z
published: 2026-04-06T16:51:05Z
canonical: "helpcenter.securiti.ai/configuring-content-profiles"
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring content profiles

Content profiles are sets of rules used to identify types of document content. Securiti includes a set of system content profiles that you can enable or create custom ones.

You can use content profiles to create file-level content-matching policies by using a collection of data element types, dictionaries, document types, file formats, regular expressions, and keywords. Content profiles act as labels that apply to a document when the system detects the first match for the defined content profile combination.

For instance:

- You can create a custom content profile to detect documents that contain **SSN**, **FNAME**, and **LNAME**. Securiti tags the document with the content profile when it finds at least one occurrence of each element in it.
- You can create custom content profiles to label documents based on the presence of keywords. For instance, you can create a **Design Document** content profile to label documents that contain design-related keywords such as **design doc**, **design document**, or **design updates**.

> [!NOTE]
> Note
> 
> Keywords are treated as complete words or phrases, not subwords. For instance, the keyword **doc** does not match the longer word **document**.

## Supported content profiles

Securiti supports structured and unstructured data content profiles.

| Geography | Structured | Unstructured |
| --- | --- | --- |
| Japan | APPI | APPI |
| United States | CPRA | CPRA |
| United States | CDTPA | CDTPA |
| United States | - | CUI |
| UK | DPA | DPA |
| India | DPDPA | DPDPA |
| United States | FERPA | - |
| European Union | GDPR | GDPR |
| United States | GLBA | GLBA |
| United States | - | ITAR |
| Brazil | LGPD | LGPD |
| United States | PA | PA |
| Global | PCI DSS | PCI DSS |
| Singapore | PDPA | PDPA |
| Saudi Arabia | PDPL | PDPL |
| Hong Kong | PDPO | PDPO |
| Pakistan | PDPPL | PDPPL |
| United States | PHI | PHI |
| Canada | PIPEDA | PIPEDA |
| China | PIPL | PIPL |
| Global | PII | PII |
| United States | VCDPA | VCDPA |

## Viewing available content profiles

To view the available content profiles:

- From the main menu, click **Sensitive Data Intelligence** > **Data Classification** > **Content Profiles**.
- Securiti opens the **Content Profiles** page, as shown below.

![Overview of content profiles, including active categories and total profiles in a system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-05 at 9.40.59 PM.png)

## Creating a custom content profile

To create a custom content profile:

1. From the main menu, click **Sensitive Data Intelligence** > **Data Classification** > **Content Profiles**.
2. On the **Content Profiles** page, near the upper right corner, click + **Add Custom Content Profile**.

![Overview of content profiles, including active categories and total profiles in a system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-05 at 9.40.59 PM(1).png)
3. From the **Select Organization** popup, choose a relevant organization from the **Organization** menu.

![Select organization dropdown in content profiles settings for data classification management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-06 at 12.59.31 PM.png)
4. On the **Add Custom Content Profile** page, apply the following settings:

![Settings page for creating a custom financial content profile with various options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-06 at 1.25.15 PM.png)

| Parameter | Description |
| --- | --- |
| Status | Enable the **Active/Inactive** toggle to activate or deactivate the content profile. |
| Content Profile Name | Enter a descriptive name for the content profile. > [!CAUTION] > Warning > > The character limit for naming classification resources and their categories is 50 characters. If a name exceeds this limit, Securiti​ shows an error message. Existing names remain unchanged. |
| Category | Choose the most appropriate category or add a new one: 1. Click **Add New**. 2. Enter the name of the custom category. 3. Press **ENTER** or **RETURN** key. 4. Select the category you added to assign the content profile. > [!NOTE] > Note > > The custom content profile category belongs to the organization in which you create it. |
| Descriptions | Enter a brief description. This is an optional parameter. |
| Locality | Choose one or more localities. This filters content profiles by region. |
| Language(s) | Choose from the available languages. This configures scanning only for documents in the selected languages. |
| Type | Select the data type for which you want to configure the content profile. - Choose **Structured Data** if the content profile is used when classifying database tables. These profiles appear when you create a discovery scan for structured data systems such as **Snowflake** or **MySQL**. - Choose **Unstructured Data** if the content profile is used when classifying files. |
| Content Profile Definitions | Set the inclusion and exclusion criteria for the content profile. These settings vary based on the selected data type. For more information, see the section below. |
| Expression | Securiti automatically generates an expression based on the selected inclusion and exclusion criteria. |

1. When you are done, near the upper right corner of the page, click **Save Content Profile**.

## Inclusion and Exclusion Criteria

When creating a custom content profile, you have to set the inclusion and exclusion criteria. Use the **Inclusion Criteria** tab to build a set of rules to include in this content profile. Similarly, use the **Exclusion Criteria** to exclude the rules from the content profiles.

> [!NOTE]
> Note
> 
> The inclusion and exclusion criteria varies for structured and unstructured data

### Criteria for Structured Data

Click the **Inclusion Criteria** and **Exclusion Criteria** tabs to specify the rules to include or exclude in the content profile. The available options for both tabs are similar:

1. Click Options (three dots icon) on the **Rule Set** bar and select either of the following:
  1. **Add New Rule**: Adds another subset of Rule Set
  2. **Add New Rule Set**: Adds a single rule
  3. **Switch to** [condition]: Switches to the other condition, such as **AND**/**OR**.

> [!NOTE]
> Note
> 
> You can use the **NOT** option to reverse the individual rules.
2. From the **Rule Type** menu, choose the available type. For structured data, the only available rule type is **Data Element**.
3. Enable **PII** or **Specific Data Element Types** from the menu.
  1. If you enable **Specific Data Element Types**, select the required data elements from the list. For instance, to build a content profile for a financial document, select **Bank Account Number** and **Bank Routing Number**.

![System settings interface displaying data classification and content profile options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-06 at 3.40.19 PM.png)
4. Set the **Minimum Unique Occurrence**, which specifies the minimum number of times the data element must appear in the document for it to be declared a content profile.
5. Securiti builds an expression based on the defined rules. You can review the complete rule using this expression.

Set the rule for the **Exclusion Criteria** in the same way.

### Criteria for Unstructured Data

Click the **Inclusion Criteria** and **Exclusion Criteria** tabs to specify the rules to include or exclude in the content profile. The available options for both tabs are similar:

1. Click Options (three dots icon) on the **Rule Set** bar and select either of the following:
  1. **Add New Rule**: Adds another subset of Rule Set
  2. **Add New Rule Set**: Adds a single rule
  3. **Switch to** [condition]: Switches to the other condition, such as **AND**/**OR**.

> [!NOTE]
> Note
> 
> You can use the **NOT** option to reverse the individual rules.
2. From the **Rule Type** menu, choose the available type. From the **Rule Type** menu, choose the available type. For unstructured data, the available rule types include:
  1. Data Element
  2. Dictionaries
  3. Document Type Categories
  4. Document Types
  5. Exact Data Profiles

> [!NOTE]
> Note
> 
> The content profiles for **Exact Data Profiles** rules work mainly for self-hosted data systems.
  6. File Format Categories
  7. File Last Modified Date

> [!NOTE]
> Note
> 
> You can include or exclude **File Last Modified Date** rule and specify a **Before** or **After** date for which you want to track the older files.
> 
> ![System settings interface showing content profile rules for file modification dates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-07 at 12.52.57 AM.png)
  8. File Name Patterns
  9. File Owners
  10. Keywords
  11. Regex

> [!NOTE]
> Note
> 
> You can use regular expressions (**regex**) to match patterns or character sequences in text for classification. Incorrect regex patterns can affect scanning performance or increase processing time. To prevent this, Securiti uses **Regular Expression Denial of Service (ReDoS)** scanners to detect inefficient patterns. For instance, when you enter an incorrect regex, Securiti detects it and displays an error message:
> 
> ![Error message indicating invalid regex in the content profile settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-07 at 1.27.37 AM.png)
> 
> If a regex is vulnerable, Securiti shows an error message on the upper right of the **Content Profiles** page highlighting the affected portion.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(990).png)
> 
> For more information, see [Regular expression denial of service](https://owasp.org/www-community/attacks/Regular_expression_Denial_of_Service_-_ReDoS).
  12. File Owner
3. Enable **PII** or **Specific Data Element Types** from the menu. If you enable **Specific Data Element Types**, select the required data elements from the list.
4. Set the **Minimum Unique Occurrence**, which specifies the minimum number of times the data element must appear in the document for it to be declared a content profile.
5. Configure the **Character Proximity** and **Character Range** for unstructured data. For more information, refer to the section below.
6. Similarly, set the rule for the **Exclusion Criteria** .
7. Securiti builds an expression based on the defined rules. You can review the complete rule using this expression.

#### Understanding Character Proximity and Character Range

**Character Proximity** lets you define the number of characters between primary and supporting data elements and works only if a rule created within the content profile contains multiple data elements. **Character Range** lets you identify the starting and ending point (in the number of characters) to begin and end searching for a term. This only applies to Keywords, Regexes, and Data Element rules.

> [!WARNING]
> Important
> 
> - When Character Proximity is enabled in a Content Profile, the system evaluates it as per the set rule. Additionally, it requires that **Minimum Unique Occurrence** is set for the rule and within the specified character range for the profile to trigger.
> - If you need the content profile to trigger on a Single data element, you must disable **Character Proximity**.

Lets explore a few examples to understand how character proximity and range works:

| Example | Defined data elements | Character Proximity and Character Range settings | Result |
| --- | --- | --- | --- |
| **Character Proximity Disabled** | Password Credit Card | **Minimum Unique Occurence**: 1 | Content Profile triggers if at least one of the data elements (Password or Credit Card) is detected. |
| **Character Proximity Enabled** | Password Credit Card | **Minimum Unique Occurence**: 2 **Character Proximity**: Enabled **Character Range**: 500 | Content Profile triggers if at least two unique data element occurrences are detected and they are within the first 500 characters of the profile. These detections may include: i. One Password and one Credit Card detection ii. Two Passwords detections iii. Two Credit Card detections |

Considering the above-mentioned examples, lets look into a real-time use case with sample data:

| Defined data element | Character Proximity and Character Range settings | Sample document Employee Information Form | How it works? |
| --- | --- | --- | --- |
| SSN (Social Security Number) DOB (Date of Birth) | **Character Proximity**: Enabled **Character** **Range**: 500 **Minimum** **Unique** **Occurence**: 2 | Name: John Doe SSN: 123-45-6789 DOB: 01/15/1985 Address: 123 Main Street, Anytown, USA Department: Engineering | When you set Character Range to 500, the system evaluates whether the configured Minimum Unique Occurrence requirement is met within the first 500 characters. In the above example, we have found that both conditions are satisfied, so the content profile would be triggered. |

For this example, the content profile would trigger if any of the following detections are made within the first 500 characters:

However, the content profile would NOT trigger if any of the following occurs:
  1. One SSN and one DOB detection
  2. Two SSN detections
  3. Two DOB detections
  1. The content profile would not trigger if any of the following detections is not made within the first 500 characters:
    1. One SSN and one DOB detection
    2. Two SSN detections
    3. Two DOB detections
  2. The content profile would not trigger if neither the SSN nor DOB is present in the set Character Range of 500.

## Viewing details of a content profile

To view the details of a content profile, on the **Content Profiles** page, click the profile to open its details panel, as shown below.

![Overview of content profiles with details on data elements and privacy regulations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-07 at 1.31.29 AM.png)

## Activating or deactivating a content profile

You can activate a content profile with or without activating its dependent CC resources, such as data elements, document categories, file formats, and exact data profiles. When you activate a content profile, Securiti displays a modal listing all dependent CC resources and provides the following options:

- If the dependent resources are inactive, you can activate them with a single click.
- If you do not want to activate the dependent resources, you can proceed by activating only the content profile.
- To activate or deactivate a content profile, select or clear the checkbox at the left edge of the profile.

You can activate a content profile with or without activating its dependent **Content Classification (CC)** resources, such as data elements, document categories, file formats, and exact data profiles. When you activate a content profile, Securiti shows a popup listing all dependent CC resources and provides the following options:

- If the dependent resources are inactive, you can activate them with a single click.
- If you do not want to activate the dependent resources, activate only the content profile.

To activate or deactivate a content profile, select or clear the checkbox at the left edge of the profile.

![Overview of content profiles including DEWA and GCC categories in system settings.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-07 at 1.37.44 AM.png)

## Renaming a custom content profile category

To rename a content profile category:

1. Next to the category name, click **Edit (pencil icon)**.

![Overview of content profiles including DEWA Green Bill and other categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-03-07 at 1.42.24 AM.png)
2. Enter the new category name.
3. Press **Enter** or **Return**.

The updated name changes appear in the discovery scan results and the **Structured**, **Unstructured**, and **Streaming Data Discovery** dashboards.

> [!NOTE]
> Note
> 
> - You can only rename the title of the custom content profile category.
> - You cannot rename the system categories.
