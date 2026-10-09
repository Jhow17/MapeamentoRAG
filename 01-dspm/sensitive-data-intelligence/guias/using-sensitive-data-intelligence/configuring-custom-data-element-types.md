---
title: "Configuring custom data element types"
slug: "configuring-custom-data-element-types"
updated: 2026-08-31T21:00:01Z
published: 2026-08-31T21:00:01Z
canonical: "helpcenter.securiti.ai/configuring-custom-data-element-types"
stale: true
area: dspm
modulo: sensitive-data-intelligence
tipo: guia
data_captura: 2026-10-06
---

# Configuring custom data element types

Data element types are basic units of data that have a unique meaning and are of distinct value. You can capture them using combinations of keywords and regular expression matches. Examples of data element types include gender, race, and geographic location.

For a list of the available system data element types, see [System data element types](/v1/docs/system-data-element-types).

Data element types help you count the number of occurrences of pieces of data within a document. For example, you can create a custom data element type to detect all the occurrences of Transaction IDs within your documents. Securiti then goes through the entire document in search of all the occurrences of the Transaction IDs you configured.

For example, if you use a 9-digit badge number to identify your employees, you can create an “Employee Badge Number” Data Element type based on a regex like \d{9}. You can also do the same thing for Customer ID, PO Numbers, Supplier ID, etc.

Another example, you could create a “Product SKU” Data Element type to track the various SKUs you might have. Such a Data Element type could be keyword-based, looking for the words that are used across your SKUs. Note that, when using keywords, the assumption is that the keyword is sensitive data. You could use similar keyword-based data element types for Account Status, Manufacturer, Industry Code, etc.

### Adding a custom data element type

> [!NOTE]
> **Note**
> 
> You may have data elements with similar data, such as credit card numbers (or some number of digits), which can be similar to driving license numbers or SSNs. When you configure a custom data element using regex patterns, keywords, or dictionaries, you can give you nearly accurate classification results. It is also possible that Securiti overrides your original data element in such a case, detecting false positives. To avoid this, you need to use a combination of regex patterns, keywords, and dictionaries, with the relevant misfiring rates (ranging from zero to medium and low to high).

1. In Securiti **Sensitive Data Intelligence**, open **Data Classification > Data Elements**.
2. From the main menu, choose Sensitive Data Intelligence > Data Classification > **Data Elements**.

![Securiti dashboard displaying sensitive data intelligence and data classification options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.33.42 PM(1).png)

This opens the **Data Elements** page as shown below:

![Overview of data elements and categories in a system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 11.14.25 PM(2).png)
3. On the Data Elements page, near the upper right corner, click **+ Add Custom Data Element Type**.
4. On the custom attribute page, enter the following information:

| **General Information** |
| --- |
| Status | Use the toggle to enable or disable the data element type. |
| Data Element Name | Enter a unique name for the attribute. > [!CAUTION] > Warning > > The character limit for naming classification resources and their categories is 50 characters. If a name exceeds this limit,​ Securiti shows an error message. Existing names remain unchanged. |
| Data Element Category | Choose the category for the custom data element type. To add a new data element category or to move it to another category, click **Add New**. Enter the name of the custom category and press **ENTER** or **RETURN** key. To move it to a new category, choose the one you added. > [!NOTE] > **Note** > > The custom data element category that you create belongs to the specific organization in which you create it. |
| Descriptions | (Optional) Enter a description of the data element type that tells other Securiti users what the attribute does. |
| Element Type | Mark checkboxes for Personal Data and Non-personal sensitive data as appropriate: **Personal Data** elements have the notion of identifiability and uniqueness to a person, for example, username, medical condition, job title, and email. When you choose Personal Data, Securiti enables you to configure the **People Data Graph** section. **Non-personal Sensitive Data** is any data that reveals sensitive information and is not tied to an individual: - Racial or ethnic origin - Political opinion - Religious or philosophical beliefs - Trade union membership - Genetic data - Biometric data - Health data - Sex life or sexual orientation In this case, define the **Scope** to choose data system type and language. |
| Special Category | (Only available when Element Type includes Personal Data) Mark the **Yes** radio button for data element types that GDPR considers special--that reveal a data subject's racial or ethnic origin, political opinions, or religious and philosophical beliefs. |
| Exclude from evidence collection | Some data elements might contain sensitive information that you don't want to be identified in evidence collection, for example, falling under the financial or authentication category. (Optional) To explicitly exclude this data element from being collected in the evidence, enable this toggle. > [!NOTE] > **Note** > > This option applies to all future scans. The scan jobs in progress or scheduled do not have any impact. |
| Limit to Exact Data Matches | (Only enabled when you link a custom data element with an exact data match index) Select the field for the exact data match. The data elements are classified only if they match the selected exact data match index. |
| Match Percentage | (Only available when you select a data element for exact data match in the previous field) It is set to the system percentage by default, which is 50%. You can enter a custom value within the range of 1 to 100 for classification. |
| **People Data Graph** |
| Identifiability | Indicate how many people can share the same value for this attribute. |
| Uniqueness | Choose the document languages from the menu. |
| **Scope** |
| Perform only column header classification | > [!NOTE] > **Note** > > This option applies only to structured data systems. Mark the **Perform only column header classification** checkbox to enable header-only classification for data elements based on your configured regex patterns. If a column header matches a configured regex pattern, Securiti classifies the column immediately without reading its content. If no match is found, Securiti runs standard classification using both the header and content based on the **Definition** field. > [!WARNING] > Important > > The **Definition** field is required to support standard classification. |
| Data System Type | Choose a relevant data system from the menu. |
| Locality | Defines the geographic region associated with the data. By default, this is enabled for all localities. |
| Language | Choose the document languages from the menu. To view supported languages, see the [List of supported languages and localities](/v1/docs/data-classifications). |
| **Configuration** |
| Column header Regex | If you enabled the **Perform only column header classification** checkbox, the **Column header Regex** options get enabled. Specify a relevant regex pattern(s) for column header classification. Regex pattern(s) take precedence over the system detectors. If the match is found, no other detection would be required. > [!NOTE] > **Note** > > We have a validation limit of a minimum of 1 and a maximum of 10 regexes that you can enter here. |
| **Definition** |
| Matching Rule | Do one of the following: - Select **Regex** and enter the correct regex for pre-defined pattern. > [!WARNING] > **Important** > > - Securiti restricts regex patterns to 500 characters. > - You must provide the [correct regex pattern](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/Pattern.html) as Securiti validates all regex patterns against ReDoS vulnerabilities during the creation of a data element or content profile. You can use these third-party tools to validate and test your regex pattern: > > If a pattern is invalid or vulnerable, Securiti does not create it, as shown below: > > ![invalidRegexDataElement.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-eae9d170-9c40-6785-ce70-630da9ad1ca6(1).png) > - [https://regex101.com](https://regex101.com) > - [https://regex-generator.olafneumann.org/](/v1/docs/securiti-pods-and-elastic-pods) When compiling patterns, Securiti automatically applies the following flags: Use the following table to understand how regex patterns are matched against content: \| Input text \| Pattern \| Match found \| \| --- \| --- \| --- \| \| `Employee ID: EMP-004821` \| `EMP-\d{6}` \| `EMP-004821` \| \| `Contact: john@example.com` \| `[\w.+-]+@[\w-]+\.[a-zA-Z]{2,}` \| `john@example.com` \| \| `SSN: 123-45-6789` \| `d{3}-d{2}-\d{4}` \| `123-45-6789` \| - `MULTILINE` is always applied. `^` and `$` match at line boundaries within the content. - `CASE_INSENSITIVE` and `UNICODE_CASE` are applied when the rule is configured as case-insensitive. - `DOTALL` is applied for certain detection types, which allows `.` to match newline characters. - Choose **Dictionary**, then select the dictionary. - Choose **Keywords** and build a list of keywords. > [!NOTE] > **Note** > > You can add multiple keywords, each with a limit of up to 50 characters. |
| Input text | Pattern | Match found |
| `Employee ID: EMP-004821` | `EMP-\d{6}` | `EMP-004821` |
| `Contact: john@example.com` | `[\w.+-]+@[\w-]+\.[a-zA-Z]{2,}` | `john@example.com` |
| `SSN: 123-45-6789` | `d{3}-d{2}-\d{4}` | `123-45-6789` |
| Case Sensitive | Case-sensitive option is available only for the Keyword option selected from the **Matching Rule** field. Choose **Yes** if the data element is case-sensitive, or choose **No** if not. |
| Expected Misfiring Rate | Enter an expected misfiring rate that captures how likely the matches identified by the regex, dictionary, or keyword rule will be incorrect and determines if additional anchors are needed: - When the misfiring rate is set to Zero or Low, we do not require anchors for detection. - When the misfiring rate is set to Moderate or High, you might provide additional anchors to aid detection For example, some data elements have very unique formats (e.g., MAC addresses) that do not require an anchor to accurately classify them. Other data elements might have formats with high misfiring rates (e.g., a bank account number or an unformatted 5-digit number), making an anchor critical to discerning if a column of data is of that type. Data that can be classified without a header only after reading many rows, such as first names or street addresses, would be Moderate. Data that cannot be classified without a strong header present, such as a bank account number or license plate number would be Very Low. |
| **Anchors** |
| Perform sub-word search | (Optional) Mark this checkbox to match anchor keywords inside larger words. When cleared, Securiti counts only whole-word matches. For example, with this option enabled, the anchor keyword `ID` also matches within `EMPLOYEEID` > [!NOTE] > Note > > By default, this checkbox is marked for existing custom data elements. You can clear it by editing the custom data element. |
| Positive Anchor Keywords | (Optional) Build a list of keywords or column headers that are likely to be found adjacent to the custom data element type in your data systems. Doing so increases the likelihood that Securiti correctly identifies the attribute in your data systems. Securiti uses the following logic: - For unstructured data, anchor terms are matched as whole words. Spaces can be included as well (e.g., “employee number”). - For structured data, anchors are used when examining table headers, so expected header terms (e.g., “EMP_NMBR”) can be directly used. Table headers are automatically split during processing, so subparts can be specified as well (e.g., “EMPID” would be found in “COMPANY_EMPID”). - For semi-structured data (JSON or XML), anchors are searched for in key strings. Key strings are split according to format prior to processing (e.g., “employee” will be processed as “employee id”). Up to three levels of keys prior to a value are considered when searching for anchor terms. |
| Negative Anchor Keywords | (Optional) Build a list of keywords or column headers that you don't want Securiti to identify as a data element. **Example** Specify employee_no, emp_num, employee_number as negative anchor keywords. |
| **AI Tuning** |
| Total Tuning Operations | View the total number of AI Tuning refinements applied to the selected data element. Additionally, click **AI Tuning History** button to directly view the AI tuning history of selected data element. > [!NOTE] > **Note** > > This option is available only for AI tuned data elements, such as the custom data elements created during AI tuning. |

1. Review the data element type to make sure that it is correctly configured.
2. Click **Create Data Element Type**.

### Viewing data element types and supported languages, and localities

This section lists the active and inactive data elements existing for your tenant.

Under the **Tenant Entitlements**, you can see a list of supported localities and languages for data element classification.

![List of active localities and languages for tenant entitlements in data elements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 11.05.54 PM(1).png)

Next is the row of widgets that show the counts of total and active data element categories and data elements.

To view the list of supported localities and languages, see [List of supported localities and languages for data classification](/v1/docs/data-classifications).

![Overview of tenant entitlements, including active localities and data element categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 10.33.02 PM(1).png)

To view the details of data element types:

- In Securiti, open **Sensitive Data Intelligence**, and choose **Data Classification > Data Elements**.

Securiti opens the Data Element Types page, as shown below.

![Overview of data elements and categories in system settings interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 11.14.25 PM(3).png)

Data element types are divided into categories and displayed on chips. You can enable or disable individual elements or entire categories of elements. In general, you should disable any elements or categories that are irrelevant to the scope of your data to improve data scanning performance.

Some chips are marked by special badges:

- **S****tars**: Attributes that GDPR defines as special categories of data that reveal a data subject's racial or ethnic origin, political opinions, or religious and philosophical beliefs.
- **Gear with sparkling effect**: Custom data element that was created during AI Tuning.

Click any data element type to open its Details panel, where you can enable or disable it and view its details, as shown below.

![Overview of system settings with highlighted data element details and categories.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-04-20 at 11.23.00 PM.png)

You can enable or disable individual data element types or entire categories of elements. When you enable a data element type, any scans initiated after that scan for the personal data. When you disable data element types, information from previous scans is not updated, but future scans will not scan for that personal data.

> [!NOTE]
> Note
> 
> For AI-tuned data elements, you can view the total number of tuning operations and navigate directly to the AI tuning history. To view the AI tuning history:
> 
> - Open the data element details page.
> - Click **AI Tuning History**.
> 
> ![System settings for data classification, including tuning operations and keyword inputs.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Screenshot 2026-02-18 at 3.52.34 PM.png)

You can also use standard Securiti filtering tools to filter the catalog of data element types. See [Filtering pages and dashboards](https://helpcenter.securiti.ai/v1/docs/filtering-securiti-pages-and-dashboards) for more information.

### Enabling or disabling an entire category of custom data element types

You can now enable a content profile with or without enabling any dependent data elements. When you enable a content profile, Securiti shows a modal that contains a list of all dependent data elements and other CC resources for which you can use the below options:

- If they are in a disabled state, you can enable them with just a click.
- If you don't want to enable them, you can just enable the content profile.

1. Mark or clear the checkbox at the left edge of the category.
2. Near the upper right corner of the page, click **Save** to save your changes.

> [!NOTE]
> **Note**
> 
> When you disable a data element, Securiti shows a modal if there are dependent content profiles in the enabled state. You can disable those content profiles and hence proceed with disabling the data element.

### Enabling or disabling a custom data element type

1. Click the chip for the data element type to open its Details panel.
2. Use the slider near the top of the Details panel to set its status to Active or Inactive.
3. Click **X** to dismiss the Details panel.
4. Near the upper right corner of the page, click **Save** to save your changes.

### Renaming a custom data element category

Once you add a custom data element, you can see a pencil icon on the category. Click that pencil icon to rename that category and press **ENTER** or **RETURN** key. The changes to these custom categories are reflected under the discovery scan results, structured, unstructured, and streaming data dashboards.

> [!NOTE]
> **Note**
> 
> You can only rename the title of the custom data element category, you cannot rename the system categories.

### Troubleshooting vulnerable regex patterns

In case of a potentially vulnerable regex pattern, Securiti shows an error message on the upper right side of the **Data Elements** page, with the vulnerable part highlighted in the regex pattern, as shown below:

![vulnerableRegexError.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-635c47f3-856c-fb60-74c5-a1169a185b65(3).png)

For a better understanding of providing a safe regex pattern, see [Regular Expression Denial of Service - ReDoS](https://owasp.org/www-community/attacks/Regular_expression_Denial_of_Service_-_ReDoS).

## Related

- [System data element types](/system-data-element-types.md)
- [Customizing system data element types](/data-elements-customizing-system-data-element-types.md)
