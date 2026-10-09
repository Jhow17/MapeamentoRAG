---
title: "Configuring Pardot Integration in Securiti"
slug: "configuring-pardot-integration-in-securiti"
updated: 2026-07-21T10:23:39Z
published: 2026-07-21T10:23:39Z
canonical: "helpcenter.securiti.ai/configuring-pardot-integration-in-securiti"
stale: true
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring Pardot Integration in Securiti

Securiti's Privacy Platform Integration (PPI) framework within the Universal Consent Management (UCM) module lets you automate consent-driven workflows with third-party systems such as **Salesforce Marketing Cloud Account Engagement (Pardot)**.

Organizations often store their data subjects' consent records in third-party marketing or Customer Relationship Management (CRM) systems such as **Pardot** and others to support marketing and communication initiatives. These records may include UUIDs, email addresses, country codes, and exceptions defined for specific purposes. However, many contacts may not have an associated consent status, creating uncertainty around whether consent is granted or not. To address this, Securiti provides two key capabilities:

- **Default Consent State** which lets you infer a consent status when none is recorded, based on location-specific regulatory guidelines. Countries may define consents as **Granted**, **Declined**, or **Restricted** by default.
- **Rules Matrix** which complements the **Default Consent State** by applying jurisdiction-specific exceptions to consent logic.

Additionally, a dedicated **Runtime Log** ensures transparency by tracking runtime activities performed through these integrations. The log shows the status, integration name, data system, instance name, object name, integration type, and time.

> [!NOTE]
> **Note**
> 
> - If this feature is not available in your Securiti tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan.
> - Only the following Securiti user roles in your organization have permission to create, read, update, and delete integration:
>   - Super Admin
>   - Org Admin

Securiti’s UCM module integrates with Salesforce Marketing Cloud Account Engagement (Pardot) through the following use cases:

| Use Case | Description |
| --- | --- |
| **Inbound integration** (from Pardot to the UCM module) | Securiti derives consent records from Pardot. If a contact already has a consent status, it is preserved. If not, Securiti applies the **Rules Matrix** and **Default Consent State** to determine and store the consent. |
| **Outbound integration** (from the UCM module to Pardot) | Securiti pushes updated consent values from UCM back to Pardot, ensuring those systems reflect current, compliant consent data. |

Securiti collects consent via preference centers, web-based consent form, consent APIs, upload consent or other configured collection points. This data flows into UCM, where it is evaluated and propagated across your connected systems. These integrations streamline compliance, reduce manual effort, and ensure up-to-date consent records.

### Prerequisites

To successfully configure the PPI in Securiti's UCM module with a third-party data system:

- Enable the **Enable Privacy Platform Integration** toggle:

> [!NOTE]
> **Important**
> 
> - When you enable the **Enable Privacy Platform Integration** toggle, Securiti lets you use a third-party data system in PPI.
> - Securiti lets you use the PPI functionality only if you have an active subscription to it, along with active subscriptions to the **Connectors**, **UCM**, and **Workflows** modules.
> - If you recently subscribed to UCM, you must also have active subscriptions for PPI, Connectors and, and Workflows modules. End-to-end functionality depends on access to all of them.
  1. In Securiti, click the jewel at the upper left corner of the page, and choose **Integrations**.
  2. From the left panel click **Monitored** and from the right panel search for the configured **Salesforce Marketing Cloud Account Engagement (Pardot)** instance.
  3. Open the configured instance and, from the left panel in **Configurations**, click **Privacy**.
  4. From the right panel, enable the **Enable Privacy Platform Integration** toggle, as explained in the [Activate the Salesforce Marketing Cloud Account Engagement - Pardot (Securiti Cloud) connector in Securiti](https://helpcenter.securiti.ai/docs/connecting-salesforce-securiti-cloud-pardot-with-securiti).
- Enable the **Consent received from third-party platform integrations** toggle to use Rules Matrix with the PPI to derive consent:
  1. In Securiti, open Universal Consent Management, and choose **Settings** > **Universal Consent Configurations**.
  2. From the Universal Consent Configurations page, enable the **Consent received from third-party platform integrations** toggle, and click **Save**, as explained in the [Using the Rules Matrix](/v1/docs/using-the-rules-matrix).

![enable_consent_received_from_third_party_salesforce.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d685ec77-33a0-d38c-8bc0-81e0d1bc4aab(1).png)
- In the UCM module, configure the following settings:
  - [Unique Subject Identifier](/v1/docs/using-the-unique-subject-identifier-setting)
  - [Processing Purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes)
  - [Consent Purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes)
  - [Custom Parameters](/v1/docs/configuring-custom-parameters)
- You must also have an active subscription to Securiti’s **Workflows** module.

#### Key considerations

Securiti outlines important behaviors and configuration constraints when working with PPI:

- If the country is not defined in Pardot using a two-letter code, it is processed as an empty value.
- Securiti does not let you update an active integration. You must first deactivate it, make the updates, and then activate it again.
- You cannot change the Operation type after you create and activate the integration.
- If you select the Bring all the data in the first time run checkbox, create the integration, and run it once, you cannot change that option later.
- If inbound and outbound integrations are active for the same third-party marketing or CRM systems such as Pardot, or others an infinite loop may occur. Securiti recommends not updating an active integration within the first 24 hours.
- Securiti skips consent records that are returned to the same system and match one already stored in UCM.
- Securiti bypasses non-critical errors such as invalid UUIDs, missing payload parameters, or incorrect country codes to keep consent processing uninterrupted.
- Securiti currently does not support country name mapping for existing integrations. To use this feature, a new integration must be created.
- Securiti supports mapping of both `integer` and `boolean` data types in custom parameters. During inbound operations, these values are converted to `string` data type to store in Universal Consent Management, and during outbound operations, they are restored to their original data types.

#### 

### Inbound integration of consents from Pardot to UCM

To configure ingestion of Pardot consent records into UCM:

1. In Securiti, open UCM, and choose **Universal Consent Management > Platform Integrations**.
2. From the upper left corner of the PPI dashboard, click **+ Add Integration**, as shown below. ![Add_Integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f10fa8f5-7ffb-534a-e7af-62268f101b82(1).png)
3. From the **Supports Data Systems** popup, click the **Salesforce Marketing Cloud Account Engagement (Pardot)** card, as shown below. ![Pardot-Selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-463305b7-c21a-7d53-3d01-57d537d73119.png)
4. On **Integration Details** popup, fill out the following fields:

| Field | Description |
| --- | --- |
| Instance | Securiti lets you select an instance from the menu. > [!NOTE] > **Important** > > Instances appear in the list only after you configure the third-party Salesforce system, enable the **Enable Privacy Platform Integration** toggle, and successfully sync the scopes in [Connectors](https://helpcenter.securiti.ai/docs/connecting-salesforce-securiti-cloud-pardot-with-securiti). Securiti then lets you use the objects of this data system in PPI. |
| Integration Name | Enter a suitable name for the integration. |
| Description | Add an appropriate description in the field, such as “Applies predefined consent rules based on country codes for automated compliance decisions”. |
| Integration Direction | Select the **Securiti ← Salesforce Marketing Cloud Account Engagement (Pardot)** direction to sync consents from Pardot to Securiti’s UCM module. > [!NOTE] > **Important** > > Proceeding beyond this point finalizes your integration direction. Once set, you can only change the direction by configuring a new integration. |
5. Once done, near the bottom of the popup, click **Save & Continue**.

Securiti creates your integration and shows you a success message near the upper right corner of the screen.
6. On the **Edit Integration** page, fill out the following fields:

| Fields | Description |
| --- | --- |
| Integration Name | Edit the integration name to suit. |
| Description | Edit the description of the integration to suit. |
| Activate Integration (toggle) | Enable the **Activate Integration** toggle if you want the integration to execute immediately after configuration is complete. |
| Object Selection | In the **Primary Object** field, type the name of the primary object or choose a relevant one from the menu. > [!NOTE] > **Note** > > The **Primary Object** comes from the configured third-party marketing or CRM system such as **Pardot**, and **Object Selection** holds essential information. It serves as the core for related data organization and actions. |
| User Identifiers (Optional) | The **User Identifiers** section is mapped to the **Unique Subject Identifier (UUID)** feature of UCM. With this, you can: - Choose the **Salesforce Marketing Cloud Account Engagement (Pardot) Fields** from the menu. - Select **Securiti** **User ID keys** from the menu. > [!NOTE] > **Important** > > You must choose appropriate fields for mapping. For instance, if you select `Name` from Salesforce Marketing Cloud Account Engagement (Pardot) Fields, you must map it to `Name`, or `First Name`, but not to `Mobile Number`. Securiti also lets you add multiple fields in the User Identifiers section. To add a new field, click **+ Add Identifiers**. |
| Consents | The Consents section is mapped to the **Processing Purposes** and **Consent Purposes** feature of UCM. With this section, Securiti lets you: - Select the object that represents the combination of processing purposes and consent purposes in **Salesforce Marketing Cloud Account Engagement (Pardot) Fields**. - Choose the processing purposes and consent purposes from the menu in **Securiti Fields**. For instance, if you have processing purposes named **Product update**, and consent purposes named **SMS** or **Phone**, it means the person has given consent to receive product updates via mobile. - Once you select the field values, you must map them to the corresponding Securiti values. To do this, click **Edit**. - From the **Consent Field Mapping** popup, map the **Salesforce Marketing Cloud Account Engagement (Pardot) Fields** values to the corresponding Securiti values, and then click **Save**. > [!NOTE] > **Note** > > Mapping values may vary across data systems. For instance, Securiti uses **Granted**, **Declined**, and **No Consent**, while your third-party marketing or CRM systems may use **Yes**, **No**, and **Don’t know**. Securiti also lets you add multiple fields in the **Consents** section. To add a new field, click **+ Add Consent**. |
| Other fields | The **Other fields** section is mapped to the **Custom Parameters** feature of UCM. With this, Securiti lets you: - Choose a custom parameter from the menu in **Securiti Fields**. - Select appropriate values to map with the custom parameter in UCM under **Salesforce Marketing Cloud Account Engagement (Pardot) Fields**. Securiti also lets you add multiple fields in the Other fields section. To add a new field, click **+ Add Field**. |
| Timestamp & Country | - To configure the ​**Timestamp**​ field in Securiti, you must select the appropriate format from the ​**Salesforce Marketing Cloud Account Engagement (Pardot)** Fields​​ menu that matches Pardot's standard format. - To configure the ​**Securiti Fields**​ named **​Country​** with ​**Salesforce Marketing Cloud Account Engagement (Pardot)** Fields​​, select a value from the menu. - You can map a different country name to ISO Alpha-2, Alpha-3 codes, and the standard country name for inbound operations. For instance, a country like Czechia can be mapped to the Czech Republic to align with the format used in third-party systems. To map a country name: > [!NOTE] > Important > > - If you already have consent stored in **​Salesforce**​ with a timestamp, lets you preserve that Salesforce standard timestamp in UCM using the ​**Timestamp​​** field. > - **Country**​ and ​**Timestamp**​ are standard fields specific to UCM. The Country field is used to drive consent based on the data subject's location. supports ISO Alpha-2 code, Alpha-3 code, standard country name and mapped country name. - Access the ​**Country Name Mapping**​ popup from the alert banner under the ​**Timestamp & Country**​​ section. - From the ​**Country Name Mapping**​ popup, under the ​**Mapping Name**​ column, click **​Add**​​ (plus icon), as shown below. ![Country name mapping table displaying various countries and their codes, highlighting Afghanistan.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/map_2.png) |
| [Exceptions](/v1/docs/using-the-rules-matrix) | To map the exceptions defined in the Securiti Fields with the corresponding Salesforce Marketing Cloud Account Engagement (Pardot) Fields, select the respective values from the menu. Securiti also lets you add multiple fields in the Exceptions section. To add a new field, click **+ Add Field**. |
| Schedule | In the **Frequency** field under the **Schedule** section, select the time at which syncing occurs based on your requirements. For instance, if you select a **15 minute** frequency, the next inbound execution will run after 15 minutes. |
| Mark the Bring all the data in the first time run | - Mark the **Bring all the data in the first time run** checkbox to transfer all consent data the first time the mapping is enabled. On subsequent edits or enablements, Securiti transfers only the delta since the previous run. - Choose the **Date** and **Time** to bring data from Pardot that was created or updated after the selected timestamp into the Securiti’s UCM module. > [!NOTE] > **Note** > > - By default, the **Date** and **Time** fields take the current date and time if not provided in the integration. > - Once the integration is complete and configured, you can not change the state of this checkbox. |
| Operation Type | In the **Operation type** section, Securiti selects **Update or Insert (Default)** by default. Inbound integration supports only upsert operations. Securiti inserts new consent records but does not update existing ones in UCM. |
| Optional Criteria | In the **Optional Criteria** section, specify conditions based on consent field values. Syncing occurs only when the defined criteria are met. Your third-party marketing or CRM systems may store a large amount of data for the selected **Primary Object**. In our case it is `Blackstone__c`, but you may want to import only specific records that meet certain conditions. For instance, to integrate data for a specific country, select the **Country (UCM)** field, enter a two-letter country code, and click **Apply**. |
7. Once you complete all fields, click **Save and Continue** near the bottom of the **Edit Integration** tab to save the integration.

> [!WARNING]
> **Caution**
> 
> If you configure **Salesforce Marketing Cloud Account Engagement (Pardot) Fields** in PPI and later modify or delete them from Pardot, it may break the integration.
8. Next to the newly created integration, enable the **Status** toggle to activate the integration.

> [!NOTE]
> **Notice**
> 
> You can complete the integration configuration and save your changes before activating the configuration. This lets you iterate and finalize settings before making them active. You can also activate the toggle directly from the **Edit Integration** tab after completing all configurations.
9. On the confirmation popup, click **Yes, Activate**.

Securiti activates the integration and shows a success message near the upper right corner of the screen.

Once the integration is activated, Securiti creates a read-only workflow in the background that runs according to the schedule set in the configuration. It generates one workflow for each integration.

> [!NOTE]
> **Important**
> 
> Securiti does not let you configure the same field value in multiple sections. For instance, if you configure the email field in the User Identifiers section, you cannot configure the same field in the Consents section.

### Outbound integration of consents from UCM to Pardot

To configure outbound delivery of consent records from UCM to Pardot:

1. In Securiti, open UCM, and choose **Universal Consent Management > Platform Integrations**.
2. From the upper left corner of the PPI dashboard, click **+ Add Integration**, as shown below.

![Add_Integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b85fbbd6-df48-1aaa-6e19-3bacf34018f7(1).png)
3. From the **Supports Data Systems** popup, click the **Salesforce Marketing Cloud Account Engagement (Pardot)** card, as shown below.

![Pardot-Selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-463305b7-c21a-7d53-3d01-57d537d73119.png)
4. On **Integration Details** popup, fill out the following fields:

| Fields | Description |
| --- | --- |
| Instance | Securiti lets you select an instance from the menu. > [!NOTE] > **Important** > > Instances appear in the list only after you configure the third-party **Salesforce** system and enable the **Enable Privacy Platform Integration** toggle in **Connectors**. Securiti then lets you use the objects of this data system in PPI. |
| Integration Name | Enter a suitable name for the integration. |
| Description | Add an appropriate description in the field, such as “Pardot outbound integration”. |
| Integration Direction | Select the **Securiti → Salesforce Marketing Cloud Account Engagement (Pardot)** direction to sync consents from Securiti’s UCM module to Pardot. > [!NOTE] > **Important** > > Proceeding beyond this point finalizes your integration direction. Once set, you can only change the direction by configuring a new integration. |
5. Near the bottom of the popup, click **Save & Continue**.

Securiti creates your outbound integration, and shows you a success message near the upper right corner of the screen.
6. On the **Edit Integration** page, fill out the following fields:

| Field | Description |
| --- | --- |
| Integration Name | Edit the integration name to suit. |
| Description | Edit the description of the integration to suit. |
| Activate Integration (toggle) | Enable the **Activate Integration** toggle if you want the integration to execute immediately after configuration is complete. |
| Object Selection | In the **Primary Object** field, type the name of the primary object or choose a relevant one from the list. |
| User Identifiers (Optional) | The **User Identifiers** section is mapped to the UUID feature of UCM. With this section, you can: - Select **Securiti User ID keys** from the menu. - Choose the **Salesforce Marketing Cloud Account Engagement (Pardot) Fields** from the menu. > [!NOTE] > **Important** > > You must choose appropriate fields for mapping. For instance, if you select `Name` from **Salesforce Marketing Cloud Account Engagement (Pardot) Fields**, you must map it to `Name`, or `First Name`, but not to `Mobile Number`. Securiti also lets you add multiple fields in the User Identifiers section. To add a new field, click **+ Add Identifiers**. |
| Consents | This section is primarily for mapping processing purposes and consent purposes configurations with Pardot fields specific to consent. With this section, Securiti lets you: - From the **Securiti Fields** menus, choose the processing purposes and consent purposes. - Select the object that represents the combination of processing purposes and consent purposes in **Salesforce Marketing Cloud Account Engagement (Pardot) Fields**. For instance, if you have processing purpose named **Product update**, and consent purposes named **SMS** or **Phone**, it means the person has given consent to receive product updates via mobile. - Once you select the field values, you must map them to the corresponding values. To do this, click **Edit**. - From the **Consent Field Mapping** popup, map the **Salesforce Marketing Cloud Account Engagement (Pardot)** values to the corresponding Securiti values, and click **Save**. > [!NOTE] > **Note** > > Mapping consent values may vary across data systems. For instance, our Securiti’s UCM module uses **Granted**, **Declined**, and **No Consent**, while your data system may use **Opt-in**, **Out-out**, and **None** consent values. Securiti also lets you add multiple fields in the **Consents** section. |
| Other fields | The **Other fields** section is primarily for mapping **Custom Parameters** feature of UCM. With this, You can: - Choose a custom parameter from the menu in **Securiti Fields**. - Select appropriate values to map the custom parameter in **Salesforce Marketing Cloud Account Engagement (Pardot) Fields** with UCM. Securiti also lets you add multiple fields in the **Other fields** section. To add a new field, click **+ Add fields**. |
| Timestamp & Country | - To configure the ​**Securiti Fields**​ named ​**Timestamp**​ with ​**Salesforce Marketing Cloud Account Engagement (Pardot)** Fields​​, choose the value from the menu. - To configure the ​**Securiti Fields**​ named ​**Country**​ with ​**Salesforce Marketing Cloud Account Engagement (Pardot)** Fields​​, select a value from the menu. > [!NOTE] > Note > > Securiti lets you choose the country name format in outbound integrations. You can send country data to third-party systems as ISO Alpha-2 Code, ISO Alpha-3 Code, or as customizable country names, as shown below. > > ![Configuration options for Timestamp and Country fields in a scheduling interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UCM_outbound.png) |
| Country | - To configure the **Securiti Fields** named **Country** with **Salesforce Marketing Cloud Account Engagement (Pardot) Fields**, select a value from the menu. - To configure the **Securiti Fields** named **Timestamp** with **Salesforce Marketing Cloud Account Engagement (Pardot) Fields**, choose the value from the menu. |
| Timestamp |
| Schedule | In the **Frequency** field under the **Schedule** section, select the times at which syncing occurs based on your requirements. For instance, if you select a **15 minute** frequency, the next outbound execution will run after 15 minutes. |
| Mark the Bring all the data in the first time run | - Mark the **Bring all the data in the first time run** checkbox to transfer all consent data the first time the mapping is enabled. On subsequent edits or enablements, Securiti transfers only the delta since the previous run. - Choose the **Date** and **Time** to bring data from **Pardot** that was created or updated after the selected timestamp into the Securiti data system. > [!NOTE] > **Note** > > By default, the **Date** and **Time** fields take the current date and time if not provided while adding integration. |
| Operation Type | In the **Operation Type** section, Securiti lets you choose either the **Update Only** or **Update or Insert (Default)** option when sending data to a third-party system. If you choose **Update Only**, only matching consent records in the third-party system are updated, and unmatched records are ignored. If you choose **Update or Insert**, matching records are updated, and non-matching records are inserted into the third-party system. |
| Optional Criteria | In the **Optional Criteria** section, specify conditions based on Consent field values. Syncing occurs only when the defined criteria are met. Securiti’s UCM module may store a large amount of data for the selected **Primary Object**, but you may want to import only specific records that meet certain conditions. For instance, to integrate data for a specific UUID, select the `UUID` field, enter a unique ID, and click **Apply**. |
| Optional Criteria | In the ​**Optional Criteria**​ section, specify conditions based on consent field values, such as ​**email**​​, ​**Source**​​, ​**Consent Source**​ or ​**Country Code**​​. Syncing occurs only when the defined criteria are met. Securiti’s ​UCM module may store a large amount of data for the selected ​Primary Object​​, but you may want to import only specific records that meet certain conditions, as shown below. ![Optional_Criteria.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-900b7f13-5668-d831-cc24-6825466789e9.png) For instance, to integrate data for a specific email, select the ​​**email​​** field, enter the address, and click ​**Apply**​​, as shown below. ![User interface for scheduling data synchronization with highlighted email property selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_OB_CS.png) To select multiple values, in the filter criteria panel, below the field name, select **​is one of​​** from the menu, as shown below. ![Scheduling settings for data synchronization with highlighted email property options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_SF_OB_1.png) Type a value, press enter after each additional value, and then click ​**Apply**​​, as shown below. ![Schedule settings for data synchronization with highlighted email property options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_SF_OB_2.png) |
7. Once you complete all fields, click **Save and Continue** at the bottom of the **Edit Integration** tab to save the integration.

> [!WARNING]
> **Caution**
> 
> If you configure the **Salesforce Marketing Cloud Account Engagement (Pardot)** fields in PPI, and later modify or delete them from Pardot data system, it may break the integration.
8. Next to the newly created integration, enable the **Status** toggle to activate the integration.

> [!NOTE]
> **Note**
> 
> You can complete the integration configuration and save your changes before activating the configuration. This lets you iterate and finalize settings before making them active. You can also activate the toggle directly from the **Edit Integration** tab after completing all configurations.
9. From the confirmation popup, click **Yes, Activate**.

Securiti activates the integration and shows a success message near the upper right corner of the screen.

Once the integration is activated, Securiti creates a read-only workflow in the background that runs according to the schedule set in the configuration. It generates one workflow for each integration.

> [!NOTE]
> **Important**
> 
> Securiti automatically creates a read-only workflow within its **Workflows** module. This workflow is **immutable** and cannot be **edited** or **modified**. This safeguard is designed to preserve the integrity of all inbound and outbound integrations, ensuring reliable and secure orchestration behavior.

A system or platform used to manage an organization's interactions with its current and potential customers. CRM systems help organizations store contact data, track communication history, manage sales pipelines, and support customer engagement across various channels such as email, phone, and marketing platforms.

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.

## Related

- [Understanding the Privacy Platform Integrations](/understanding-the-privacy-platform-integrations.md)
- [Configuring Salesforce Integration in Securiti](/configuring-salesforce-integration-in-securiti.md)
- [Using the Privacy Platform Integrations Runtime Logs](/using-the-privacy-platform-integrations-runtime-logs.md)
- [Using the Privacy Platform Integrations Audit Log](/using-the-privacy-platform-integrations-audit-log.md)
