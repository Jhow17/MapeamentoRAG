---
title: "Using the Rules Matrix"
slug: "using-the-rules-matrix"
status: "update"
updated: 2026-03-31T11:42:35Z
published: 2026-03-31T11:43:16Z
canonical: "helpcenter.securiti.ai/using-the-rules-matrix"
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Using the Rules Matrix

**Scenario**

As a Data Privacy Officer, ensuring marketing campaigns comply with consent laws across jurisdictions can be complex. Regulations such as GDPR, LGPD, along with region-specific B2B exemptions introduce varying requirements based on geography. The Rules Matrix in Universal Consent Management automatically evaluates each data subject’s location and applies the appropriate jurisdiction-specific rules to derive the correct consent state. For instance, a contact in Spain may require prior consent for marketing emails, while a contact in the U.S. may not. You can use predefined system rules or configure custom rules to align with internal policies. This reduces compliance risk and removes the need for manual rule tracking as laws evolve.

The Rules Matrix functionality lets you manage consent compliance for direct marketing by applying jurisdiction-specific rules. It helps you identify which data subjects you can legally communicate with based on jurisdiction and compliance type, reducing compliance risks. This functionality includes predefined **System** rules and **Custom** rules to suit your business needs across multiple countries, aligning with GDPR, LGPD, and other regulations.

> [!NOTE]
> **Note**
> 
> - If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> - Only the following Securiti user roles in your organization have permission to create, read, update, and deactivate rules, while all others have READ permissions:
>   - Super Admin
>   - Org Admin
>   - Module Owner

Managing direct marketing consent in multiple jurisdictions is challenging due to differences in granted and declined requirements. These rules vary by country and scenario, such as B2B communications or existing business relationships. Non-compliance can lead to regulatory penalties, legal action, or reputational damage. Rules Matrix simplifies jurisdiction-based consent management and gives you full control over predefined and custom rule configurations.

![Rules matrix displaying consent states and exceptions for various countries and locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-1.png)

You can view and modify predefined values, adjusting the following compliance framework at the tenant level:

| Compliance framework | Description |
| --- | --- |
| Granted | Refers to a state where consent is assumed valid by default unless explicitly withdrawn or declined, allowing direct marketing communications. |
| Declined | Refers to a state where valid consent has not been obtained, prohibiting direct marketing communications until consent is properly collected. |
| Restricted | Refers to a state where direct marketing communications are not allowed, regardless of consent state, due to legal or policy restrictions. |

### Prerequisites

To configure the Rules Matrix in Securiti's UCM system:

- You must have an active subscription to the **Rules Matrix** functionality.
- Enable the Consent uploads/API toggle from the Universal Consent Configurations page. For more information, see the [Universal Consent Configurations](/v1/docs/universal-consent-configurations).

> [!NOTE]
> **Important**
> 
> - Securiti lets you derive consent statuses using the two-letter country code based on jurisdiction-specific exceptions and the **Default Consent State**. For instance, if you want to derive consent for Brazil under a **Business to Business (B2B)** subrule, you must set the value of the location parameter to `BR` in the payload. You can also derive consent statuses based on one or multiple exceptions and populate the results on the Universal Consent Management dashboard.
> - The **Default** rule takes precedence in the following cases:
>   - If the API payload does not provide a rule location.
>   - If the specified location is disabled.
>   - If the specified two-letter location code is incorrect.
>   - If you specify `default` in the location parameter in the API payload, the **Default** rule takes precedence.

With the Rules Matrix, you can:

- Filter out the existing **System**, or **Custom** rules from the dashboard by combining the following properties:

![Filters for property status in the Rules Matrix interface, showing activated and deactivated options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-2(1).png)
  - Status such as **Activated** or **Deactivated**
  - Rule Type such as **Custom** or **System**
  - Default Consent State such as **Declined**, **Granted**, and **Restricted**
  - Exceptions Granted such as B2B, Existing Business Relationship, Reasonable Expectations, Distributorship Agreement, and Publicly Available Contact Information
  - Exceptions Declined such as B2B, Existing Business Relationship, Reasonable Expectations, Distributorship Agreement, and Publicly Available Contact Information.
- View detailed metadata of any rule, as shown below.

![Rules Matrix displaying consent statuses for various countries, highlighting the United Arab Emirates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-3.png)
- Import predefined **System** rules from the master library to the Rules Matrix.
- Create **Custom** rules based on location or add a single default rule to the Rules Matrix, which applies to all locations.
- Sync all changes to update the rules to align with the updated Securiti-defined rules.
- Set different consent states for the exceptions of Securiti’s predefined system rules and your custom rules. For instance, you can set a **Granted** consent state for three exceptions and a **Declined** consent state for the remaining three exceptions of the same rule.
- Filter derived consents by applied rule using the **Filter** at the upper right of the dashboard.
- Edit and copy both types of rules individually.
- Restore modified predefined System rules individually or in bulk.
- Activate, deactivate, and delete both types of rules individually or in bulk.
- Export rules in **CSV**, **JSON**, and **Excel** file formats.
- Share them with internal stakeholders for collaboration.
- Leverage the detailed audit log exclusive to the rules, which records all actions for transparency.

![Rules Matrix displaying consent statuses and actions for various countries and locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-4.png)

> [!NOTE]
> **Important**
> 
> - Securiti lets you use this functionality to derive consent statuses via the following APIs:
>   - [Schedule consent for upload via Rules Matrix](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Consent%20upload)
>   - [Bulk import consents via Rules Matrix](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Bulk_import_consents)
>   - [Bulk import consents via CSV via Rules Matrix](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html#operation/Bulk_import_consents_via_csv)
> 
> - You must enable the **Consent uploads/API** and **Consent received from third-party platform integrations** toggles from the **Universal Consent Management Configurations** page, as shown below.
> 
> ![rules_matrix_universal_consent_configurations.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4450466e-e0eb-8729-5886-51cf47326ba4.png)
> 
> - It lets you derive consent statuses using the two-letter country code based on jurisdiction-specific exceptions and the **Default Consent State**. For instance, if you want to derive consent for **Brazil** under a **Business to Business (B2B)** subrule, you must set the value of the location parameter to `BR` in the payload. You can also derive consent statuses based on one or multiple exceptions and populate the results on the Universal Consent Management dashboard.

### Rules Matrix definitions

Use the following table to understand the definitions of rules and other key terms used in the Rules Matrix documentation:

| Term | Definition |
| --- | --- |
| Direct Marketing Communications | In the Rules Matrix, direct marketing communications include email, SMS, phone calls, and fax marketing. For call or SMS marketing, each jurisdiction may have a Do Not Call registry. In that case, you must verify recipients’ contact details against relevant registries before outreach. The current U.S. regulatory rules in Securiti’s Rules Matrix are designed exclusively for consent and processing purposes configured for email marketing. When these rules are enabled, all direct marketing consent, regardless of channel, is evaluated using the same email-specific rules. This means: - All consent and processing purposes are treated as email marketing, even if you're collecting consent for SMS, phone, mail, or fax outreach. - Non-email channels (such as SMS, phone, mail, and fax) are not supported under U.S. rules at this stage. As a result, Securiti does not recommend using U.S. rules for non-email marketing until broader channel-specific support becomes available. This same limitation applies to **Finland**, **Switzerland**, the **United Kingdom**, **France**, and **Norway**, where call marketing rules are also not yet supported based on our regulatory research. Future enhancements to Rules Matrix will extend support to additional direct marketing channels in these regions. |
| Default Consent State | The Rules Matrix provides a **Declined**, **Granted**, or **Restricted** value to each jurisdiction in the Default Consent State. This state defines the required consent for sending direct marketing communications before any exceptions apply. If no exceptions apply, it determines whether direct marketing communications can be sent. |
| Business to Business (B2B) | Applies when direct marketing communications are sent to business contacts in their professional capacity or when an email address is publicly listed for business use. |
| Existing Business Relationship | Applies when direct marketing communications of similar products or services are sent to existing customers based on their previous purchases, negotiations, or ongoing contracts (such as service agreements, NDAs, etc.). |
| Distributorship Agreement | Applies when a distribution agreement includes provisions that allow direct marketing communications to be sent to the distributor’s employees or advisors. |
| Reasonable Expectations | Applies when contacts knowingly or directly provide their contact details and expect to receive direct marketing communications. |
| Publicly Available Contact Information | Applies when contact details are publicly listed, such as on a website or brochure, without a disclaimer against direct marketing communications, or are sourced from public records. |
| Granted | Refers to a state where consent is assumed valid by default unless explicitly withdrawn or declined, allowing direct marketing communications. |
| Declined | Refers to a state where valid consent has not been obtained, prohibiting direct marketing communications until consent is properly collected. |
| Restricted | Refers to a state where direct marketing communications are not allowed, regardless of consent state, due to legal or policy restrictions. |
| Sync | Sync action updates the rules to align with the updated Securiti-defined rules, ensuring compliance with applicable location-based laws. |
| Restore | Restore action reverts any manual edits made to Securiti-defined rules, restoring them to their original version. |

### Using the top-level filter

The top-level filter lets you combine different properties of the Rules Matrix and apply filters accordingly. It takes precedence over other filters, working from the top down and determining the result values in the grid view.

To use the top-level filter:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent** > **Rules Matrix**.
2. From the upper left corner of the Rules Matrix dashboard, click **+**, as shown below.

![Rules matrix displaying consent statuses and exceptions for various countries and locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-5.png)
3. On the popup, either search by rule type or use the out-of-the-box listed properties.

For instance, if you want to filter rules by status (property), click **Status**, and from the available list on the right, mark the radio button next to the status you want to filter by. Once selected, near the bottom of the popup, click **Apply**, as shown below.

![User interface showing rules matrix with activated status option highlighted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-6.png)
4. Repeat the same step for other properties according to your search needs. Once you apply all required properties, near the bottom of the popup, click **Apply**. Securiti builds a query based on your selected properties and displays the filtered results, as shown below.

![Rules Matrix displaying consent statuses and exceptions for various countries.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-7.png)
5. To clear the top-level filter, from the upper right corner, click **Clear Search**, as shown below.

![Rules Matrix interface showing activated status and consent state options for agreements.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-8.png)

### Adding new Custom rules

Securiti lets you easily add Custom rules to the Rules Matrix for each new location or set a default rule for all unspecified locations. You can add as many Custom rules as needed, and this functionality provides full control over the management of rules.

![Interface for adding rules in a consent management system with declined options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-9.png)

> [!NOTE]
> **Note**
> 
> Securiti lets you add only one default rule at any given time. If a default rule exists in the Rules Matrix, the **Default (Everywhere)** radio button in the **Add Rule** popup is disabled. However, you can still add Custom rules based on location to meet jurisdictional requirements, as shown below.
> 
> ![Interface for adding rules in Universal Consent Management with highlighted options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-10(1).png)

Use the following table to understand potential use cases for adding new Custom rules to the Rules Matrix:

| Use Case | Description |
| --- | --- |
| Adapting to Regulatory Changes | If a jurisdiction updates its data protection laws, Securiti lets you update the compliance framework, including **Granted**, **Declined**, or **Restricted**. Rules Matrix ensures compliance by applying the latest consent model without system-wide updates. |
| Handling Industry-Specific Compliance Needs | If an organization, business, or industry such as finance or healthcare, has additional compliance requirements, Custom rules help meet sector-specific obligations while maintaining regulatory alignment. |
| Accommodating Internal Business Policies | If your organization enforces stricter data protection policies than legal mandates, Custom rules let you apply internal privacy standards alongside Securiti-defined regulations. |
| Granting Exceptions for Specific User Groups | If a regulation mandates different consent requirements for specific groups, such as data subjects, custom rules let you configure compliance while maintaining regulatory adherence. |

#### Key considerations

You must consider the following points when importing predefined System rules or adding Custom rules:

- Securiti does not let you import either a predefined or a custom rule with the same location if one already exists on the Rules Matrix dashboard. For instance, if you try to add a rule for **Brazil** and a custom rule already exists for that location, the **Add Rule** popup disables the particular location option, and vice versa.
- If the **Default Consent State** is set to **Granted**, Securiti ignores all exceptions to it, whether predefined or modified.

#### Procedure

To create a new Custom rules based on location or add a single default rule:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Rules Matrix**.
2. On the Rules Matrix page, from the upper right corner, click **+ Add Rule**, as shown below.

![Interface showing the Rules Matrix with options to add rules and search filters.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-11.png)
3. On the **Add Rule** popup:

> [!WARNING]
> **Caution**
> 
> Securiti also lets you change the compliance framework value of the **Default Consent State** to **Restricted**. When you do, Securiti assigns a **DECLINED** status to all consents from restricted countries, regardless of their existing consent status. No exceptions apply for consents from restricted countries.

| Term | Definition |
| --- | --- |
| Default Consent State | The Rules Matrix provides a **Declined**, **Granted**, or **Restricted** value to each jurisdiction in the Default Consent State. This state defines the required consent for sending direct marketing communications before any exceptions apply. If no exceptions apply, it determines whether direct marketing communications can be sent. |
| Business to Business (B2B) | Applies when direct marketing communications are sent to business contacts in their professional capacity or when an email address is publicly listed for business use. |
| Existing Business Relationship | Applies when direct marketing communications of similar products or services are sent to existing customers based on their previous purchases, negotiations, or ongoing contracts (such as service agreements, NDAs, etc.). |
| Distributorship Agreement | Applies when a distribution agreement includes provisions that allow direct marketing communications to be sent to the distributor’s employees or advisors. |
| Reasonable Expectations | Applies when contacts knowingly or directly provide their contact details and expect to receive direct marketing communications. |
| Publicly Available Contact Information | Applies when contact details are publicly listed, such as on a website or brochure, without a disclaimer against direct marketing communications, or are sourced from public records. |
  1. Mark the **Default (Everywhere)** radio button to create default rules for all locations or mark **Select Location** to add a custom rule for a specific location, as shown below.

![Interface for adding rules, highlighting Albania and consent states in a management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-12.png)
  2. Choose the compliance framework, such as **Declined** or **Granted** based on jurisdictional rules for the following default consent state and exceptions:
4. Near the bottom of the popup, click **Add**, as shown below.

![Rules matrix for consent management showing granted and declined statuses for various locations.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-13.png)

### 

### Importing predefined System rules

Import functionality lets you import Securiti-defined system rules into the Rules Matrix dashboard. It includes predefined rules for **58 countries (locations)**, aligning with GDPR, LGPD, and other regulations. You can import one or multiple rules at a time into the Rules Matrix dashboard to suit your business needs.

To import System rules to the Rules Matrix:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Rules Matrix**.
2. On the Rules Matrix page, from the upper right corner, click **Import**, as shown below.

![Rules Matrix interface showing filters and an import option for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-14.png)
3. On the **Import Rules** popup, search for the desired location via the search bar or mark the checkbox next to the location whose rules you want to add to the Rules Matrix. Additionally, Securiti lets you import multiple rules at once.
4. Once done, near the bottom of the popup, click **Import Rules**, as shown below.

![Import rules interface showing location options for compliance with privacy laws.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-15.png)

> [!NOTE]
> **Note**
> 
> Securiti lets you view rule details for the selected location, including **Name**, **Type**, and **Current Value**, as shown below.
> 
> ![Import rules for Canada showing consent states and agreements in a privacy management tool.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-17.png)

### Predefined (OOTB) rules for countries

Securiti provides predefined rules for **58 countries (locations)** out of the box. These rules are based on research completed by our team of **Data Privacy Legal Analysts** across multiple countries.

Securiti continuously expands coverage by adding new countries and rules as our legal research progresses. If your country of interest isn’t listed, you can create a custom rule. The Rules Matrix is designed to evolve over time through regular updates that enhance country-specific compliance options.

> [!NOTE]
> **Note**
> 
> Securiti will continue to add more country-specific rules in future releases as legal research expands.

Use the following table to know which out-of-the-box predefined rules Securiti offers:

| Country | Country code |
| --- | --- |
| Argentina | `AR` |
| Australia | `AU` |
| Austria | `AT` |
| Bahrain | `BH` |
| Belgium | `BE` |
| Brazil | `BR` |
| Canada | `CA` |
| Chile | `CL` |
| China | `CN` |
| Colombia | `CO` |
| Costa Rica | `CR` |
| Cyprus | `CY` |
| Denmark | `DK` |
| Dominican Republic | `DO` |
| Egypt | `EG` |
| Finland | `FI` |
| France | `FR` |
| Georgia | `GE` |
| Honduras | `HN` |
| Hong Kong | `HK` |
| Hungary | `HU` |
| Iceland | `IS` |
| India | `IN` |
| Indonesia | `ID` |
| Ireland | `IE` |
| Israel | `IL` |
| Italy | `IT` |
| Japan | `JP` |
| Jordan | `JO` |
| Kuwait | `KW` |
| Lebanon | `LB` |
| Liechtenstein | `LI` |
| Luxembourg | `LU` |
| Mexico | `MX` |
| Monaco | `MC` |
| Netherlands | `NL` |
| Norway | `NO` |
| Oman | `OM` |
| Panama | `PA` |
| Peru | `PE` |
| Portugal | `PT` |
| Qatar | `QA` |
| Russia | `RU` |
| Saudi Arabia | `SA` |
| Singapore | `SG` |
| South Africa | `ZA` |
| South Korea | `KR` |
| Spain | `ES` |
| Sweden | `SE` |
| Switzerland | `CH` |
| Syria | `CY` |
| Taiwan | `TW` |
| Thailand | `TH` |
| Turkey | `TR` |
| United Arab Emirates (UAE) | `AE` |
| United Kingdom (UK) | `GB` |
| United States of America (USA) | `US` |
| Uruguay | `UY` |

### Syncing rules with latest changes

With the **Sync All Changes** functionality, Securiti lets you update the rules and align them with updated Securiti-defined rules to ensure compliance with applicable location-based laws and regulations. Sync All Changes option remains disabled until Securiti updates the predefined rules, as shown below.

![Rules Matrix interface showing filters, search bar, and sync changes option.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-18.png)

### Editing rules

Securiti lets you update the compliance framework values of both predefined and custom rules.

> [!WARNING]
> **Caution**
> 
> Securiti does not recommend changing the **Default Consent State** from **Declined** to **Granted**. When set to Granted, all exceptions to the Default Consent State, whether predefined by Securiti or modified by you, are ignored. To apply Securiti-defined rules, you must restore them to their default state.
> 
> ![Editing consent rules with highlighted warnings and options for different business relationships.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-19.png)

To edit the rules:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Rules Matrix**.
2. From the right side of the location whose rules you want to edit, click **Options** (three dots) and select **Edit**, as shown below.

![Rules Matrix displaying consent statuses for various countries, highlighting the United Arab Emirates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-20.png)
3. On the **Edit Rule** popup, change the compliance framework values, such as **Granted** or **Declined**, based on your business needs.

> [!WARNING]
> **Caution**
> 
> Securiti also lets you change the compliance framework value of the **Default Consent State** to **Restricted**. When you do, Securiti assigns a DECLINED status to all consents from restricted countries, regardless of their existing consent status. No exceptions apply for consents from restricted countries.
4. Once done, near the bottom of the popup, click **Save**, as shown below.

![Editing consent rules for various countries, highlighting granted and declined statuses.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-21.png)

> [!NOTE]
> **Note**
> 
> It may take up to 10 minutes to apply changes to the consent.

### Restoring the System rules individually

Securiti lets you restore only predefined system rules. If you edit compliance framework values, such as **Granted**, **Declined**, or **Restricted**, and want to revert, you can restore them to Securiti-defined rules.

To restore a single System rule:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Rules Matrix**.
2. From the right side of the location whose rules you want to restore, click **Options** (three dots) and select **Restore**, as shown below.

![Rules Matrix displaying consent statuses for various countries, highlighting the United Arab Emirates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-22.png)
3. On the **Restore** popup, review the current and new compliance framework values of modified rules.
4. Once the review is done, near the bottom of the popup, click **Restore**, as shown below.

![Restore options for United Arab Emirates with current and new values displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-23.png)

### Restoring the System rules in bulk

To restore System rules in bulk:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Rules Matrix**.
2. From the left side, mark the checkboxes next to the **Status** toggle whose rules you want to restore. Then, from the action toolbar above the rules list, click ​**Restore**​​, as shown below.

![Rules Matrix showing consent statuses for various countries, highlighting declined exceptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-24.png)
3. On the **Restore** popup, review the current and new compliance framework values of modified rules.
4. Near the bottom of the popup, click **Restore**, as shown below.

![Reviewing updates for locations and rules in the Securiti platform interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-25(1).png)

### Copy rules

Securiti lets you copy both System and Custom rules and apply them to multiple locations. When you copy and apply rules from one location to another, its compliance framework updates to match the copied rule values.

To copy the rules:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent > Rules Matrix**.
2. From the right side of the location whose rules you want to copy, click **Options** (three dots) and select **Copy**, as shown below.

![Rules matrix displaying consent statuses for various countries, highlighting the copy process.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-26(1).png)
3. On the confirmation popup, search for the location and mark the checkbox next to it to apply the copied rules, as shown below.

![Copying rules from United Arab Emirates to Bahrain in the Rules Matrix interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-COPY.png)

> [!NOTE]
> **Note**
> 
> Securiti also lets you copy one rule to multiple locations at once, as shown below.
> 
> ![Copying rules from United Arab Emirates to Bahrain, Oman, and Kuwait in the interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-27.png)
4. Near the bottom of the popup, click **Copy**, as shown below.

![Interface for copying rules between locations in a consent management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-28.png)

### Activating and Deactivating rules individually

You can activate or deactivate both types of rules individually. When activated, a rule applies consent values to records in the specified geolocation. When deactivated, it no longer applies to them.

To activate a single rule:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent** > **Rules Matrix**.
2. From the left side, enable the toggle next to the location where you want to activate rules, as shown below.

![Rules matrix displaying consent statuses for various countries, highlighting the activate/deactivate toggle.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-29.png)
3. On the confirmation popup, click **Yes, Activate**, as shown below.

![Confirmation prompt for activating consent rules in the Universal Consent Management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-30.png)

To deactivate a single rule:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent** > **Rules Matrix**.
2. From the left side, disable the toggle next to the location where you want to deactivate rules, as shown below.

![Rules Matrix displaying consent statuses for various countries, highlighting the United Arab Emirates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-31.png)
3. On the confirmation popup, click **Yes, Deactivate**, as shown below.

![Confirmation prompt for deactivating a rule in the Rules Matrix interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-32.png)

### Activating and Deactivating rules in bulk

To activate rules in bulk:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent** > **Rules Matrix**.
2. From the left side, mark checkboxes next to the locations where you want to activate rules. Then, from the action toolbar above the rules list, click ​**Activate**​​, as shown below.

![Rules Matrix displaying consent statuses for various countries and activation options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-33.png)
3. On the confirmation popup, click **Yes, Activate**, as shown below.

![Confirmation prompt for activating three rules in the consent management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-34.png)

To deactivate rules in bulk:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent** > **Rules Matrix**.
2. From the left side, mark checkboxes next to the locations where you want to deactivate rules. Then, from the action toolbar above the rules list, click ​**Deactivate**​​, as shown below.

![Rules Matrix displaying consent statuses for various countries and exceptions granted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-35.png)
3. On the confirmation popup, click **Yes, Deactivate**, as shown below.

![Confirmation prompt for deactivating three rules in the consent management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-36.png)

### Deleting rules

Securiti lets you delete both types of rules from the Rules Matrix to manage unapplied rules effectively. When deleted, a rule no longer applies consent values to record in the specified geolocation.

#### Deleting rules individually

To delete a single rule:

1. In Securiti open **Universal Consent Management** and choose **Universal Consent** > **Rules Matrix**.
2. From the right side of the location whose rules you want to delete, click **Options** (three dots) and select **Delete**, as shown below.

![Rules Matrix showing consent statuses for various countries, highlighting the delete operation.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-37.png)
3. On the confirmation popup, click **Yes, Delete** to delete it from the Rules Matrix, as shown below.

![Confirmation dialog asking to delete a rule in the consent management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-38.png)

#### Deleting rules in bulk

To delete rules in bulk:

1. In Securiti, open **Universal Consent Management** and choose **Universal Consent** > **Rules Matrix**.
2. From the left side, mark the checkboxes next to the location whose rules you want to delete. Then, from the action toolbar above the rules list, click **​Delete**​​, as shown below.

![Rules Matrix displaying consent statuses for various countries and their exceptions.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-39.png)
3. On the confirmation popup, click **Yes, Delete** to delete them from the Rules Matrix, as shown below.

![Confirmation prompt for deleting three selected rules in the consent management system.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-40.png)

### Sharing and exporting rules information individually

You can share rule information with stakeholders via email, including a custom message. You can also export selected search results in `CSV`, `JSON`, or `Excel` file format.

To share the information of a single rule with others:

1. From the left side, mark the checkbox next to the location whose rule information you want to share. Then, near the upper right corner of the Rules Matrix page, click **Actions**, and select **Share**, as shown below.

![Rules Matrix showing consent statuses for various countries, highlighting the United Arab Emirates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-41.png)
2. On the Share popup:

![Sharing rules matrix information via email with recipient details and file format options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-42.png)
  1. From the **File Format** menu, select a file format such as `CSV`, `JSON`, or `Excel`.
  2. From the **Add Recipients** field, select the stakeholders with whom you share the rules information. Securiti also lets you add the email address of the stakeholders.
  3. In the **Message** field, type your custom email message for the selected recipients.
  4. Once done, near the bottom of the popup, click **Share**, as shown below.

Securiti sends out emails to your selected recipients and shows you a success message near the upper right corner of the screen, as shown below.

![Rules Matrix displaying consent statuses for various countries and exceptions granted or declined.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-43.png)

To export the rule information:

1. From the left side, mark the checkbox next to the location whose rule information you want to export. Then, near the upper right corner of the Rules Matrix page, click **Actions**, and select **Export**, as shown below.

![Rules Matrix showing consent states for various countries, highlighting the United Arab Emirates.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-44.png)
2. On the export popup:
  1. From the Export as menu, select the file format in which you want to export the information of rules such as `CSV`, `JSON`, or `Excel`.
  2. Once done, near the bottom of the popup, click **Export**, as shown below.

![Export options for a report in the Rules Matrix interface, including CSV format selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-45.png)

Securiti schedules your export and shows you a success message near the upper right corner of the screen.

### Sharing and exporting rules information in bulk

To share the rules information with others in bulk:

1. Mark the checkboxes next to the location whose rules information you want to share with other users. Then, from the action toolbar above the rules list, click ​**Share**​​, as shown below.

![Rules Matrix displaying consent statuses for various countries and exceptions granted.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-46.png)
2. On the **Share** popup:
  1. From the **File Format** menu, select a file format such as `CSV`, `JSON`, or `Excel`.
  2. From the **Add Recipients** field, select the stakeholders with whom you share the rules information. Securiti also lets you search and add the email address of the stakeholders.
  3. In the **Message** field, type your email message for the selected recipients.
  4. Near the bottom of the popup, click **Share**, as shown below.

![Sharing rules matrix information via email with recipient details and file format options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-47.png)

Securiti sends out emails to your selected recipients and shows you a success message near the upper right corner of the screen.

To export the rule information in bulk:

1. Mark the checkboxes next to the location whose rules information you want to export.
2. From the action toolbar above the rules list, click ​**Export**​​, as shown below.

![Rules matrix showing consent statuses for various countries, highlighting exceptions and granted states.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-48.png)
3. On the **Export** popup:

![Export options for a report in CSV format with action buttons displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/RM-49.png)
  1. From the **Export** as menu, select a file format in which you want to export the rules information such as `CSV`, `JSON`, or `Excel`.
  2. Once done, near the bottom of the popup, click **Export**, as shown below.

Securiti schedules your export, and shows you a success message near the upper right corner of the screen.

The General Data Protection Regulation (GDPR) is an European Union (EU) regulation on information privacy. It aims to ensure the protection of personal information through a human rights-centric approach, and imposes obligations onto organizations anywhere, so long as they target or collect data related to people in the EU.

Lei Geral de Proteção de Dados (LGPD) or simply called General Data Protection Law is Brazil’s first comprehensive legislation aimed at protecting the fundamental right of privacy. It applies to every natural person or legal entity, either public or private, that handles personal data of Brazilian citizens. The LGPD can also apply extraterritorially similar to the GDPR. You can choose between Global or LGPD template in Privacy Notice Management module.

## Related

- [Visualizing the Rules Matrix flow](/visualizing-the-rules-matrix-flow.md)
- [Understanding the Privacy Platform Integrations](/understanding-the-privacy-platform-integrations.md)
- [Consent uploads via UI](/consent-uploads-via-ui.md)
- [Collecting form consent](/collecting-form-consent.md)
