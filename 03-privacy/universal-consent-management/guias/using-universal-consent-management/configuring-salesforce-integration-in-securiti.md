---
title: "Configuring Salesforce Integration in Securiti"
slug: "configuring-salesforce-integration-in-securiti"
updated: 2026-07-21T10:23:51Z
published: 2026-07-21T10:23:51Z
canonical: "helpcenter.securiti.ai/configuring-salesforce-integration-in-securiti"
stale: true
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Configuring Salesforce Integration in Securiti

Securiti's Privacy Platform Integration (PPI) framework within the Universal Consent Management (UCM) module lets you automate consent-driven workflows with third-party systems such as **Salesforce**.

Organizations often store their data subjects' consent records in third-party marketing or Customer Relationship Management (CRM) systems such as **Salesforce** and others to support marketing and communication initiatives. These records may include UUIDs, email addresses, country codes, and exceptions defined for specific purposes. However, many contacts may not have an associated consent status, creating uncertainty around whether consent is granted or not. To address this, Securiti provides two key capabilities:

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

Securiti’s UCM module integrates with Salesforce through the following use cases:

| Use Case | Description |
| --- | --- |
| **Inbound integration** (from Salesforce to the UCM module) | Securiti derives consent records from Salesforce. If a contact already has a consent status, it is preserved. If not, Securiti applies the **Rules Matrix** and **Default Consent State** to determine and store the consent. |
| **Outbound integration** (from the UCM module to Salesforce) | Securiti pushes updated consent values from UCM back to third-party systems, such as **Salesforce**, ensuring those systems reflect current, compliant consent data. |

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
  2. From the left panel click **Monitored Data Systems** and from the right panel search for the configured **Salesforce** instance.
  3. Open the configured **Salesforce** instance and, from the left panel in **Configurations**, click **Privacy**.
  4. From the right panel, enable **Enable Privacy Platform Integration** toggle as explained in the [Activate the Salesforce (Securiti Cloud) connectors in Securiti](https://helpcenter.securiti.ai/docs/connecting-salesforce-securiti-cloud-with-securiti).
- Enable the **Consent received from third-party platform integrations** toggle to use Rules Matrix with the PPI to drive consent:
  1. In Securiti, open Universal Consent Management, and choose **Settings > Universal Consent Configurations**.
  2. From the Universal Consent Configurations page, enable the **Consent received from third-party platform integrations** toggle and click **Save**, as explained in the [Using the Rules Matrix](/v1/docs/using-the-rules-matrix).

![enable_consent_received_from_third_party_salesforce.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d685ec77-33a0-d38c-8bc0-81e0d1bc4aab.png)
- In the UCM module, configure the following settings:
  - [Unique Subject Identifier](/v1/docs/using-the-unique-subject-identifier-setting)
  - [Processing Purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes)
  - [Consent Purposes](/v1/docs/configuring-processing-purposes-and-consent-purposes)
  - [Custom Parameters](/v1/docs/configuring-custom-parameters)
- You must also have an active subscription to Securiti’s **Workflows** module.

#### **Key considerations**

Securiti outlines important behaviors and configuration constraints when working with PPI:

- Securiti does not let you update an active integration. You must first deactivate it, make the updates, and then activate it again.
- You cannot change the Operation type after you create and activate the integration.
- If you select the **Bring all the data in the first time run** checkbox, create the integration, and run it once, you cannot change that option later.
- If inbound and outbound integrations are active for the same third-party marketing or CRM systems such as **Salesforce**, or others an infinite loop may occur. Securiti recommends not updating an active integration within the first 24 hours.
- Securiti skips consent records that are returned to the same system and match one already stored in UCM.
- Securiti bypasses non-critical errors such as invalid UUIDs, missing payload parameters, or incorrect country codes to keep consent processing uninterrupted.
- Securiti currently does not support country name mapping for existing integrations. To use this feature, a new integration must be created.
- Securiti supports mapping of the `integer`​ data type in UUIDs, and both ​`integer` and `boolean` ​data types in custom parameters. During inbound operations, these values are converted to `string` ​​​data type to store in Universal Consent Management, and during outbound operations, they are restored to their original data types.

### Inbound integration of consents from Salesforce to UCM

To configure ingestion of Salesforce consent records into UCM:

1. In Securiti, open UCM, and choose **Universal Consent Management > Platform Integrations**.
2. From the upper left corner of the PPI dashboard, click **+ Add Integration**, as shown below.

![Add_Integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f10fa8f5-7ffb-534a-e7af-62268f101b82.png)
3. From the **Supports Data Systems** popup, click the **Salesforce** card, as shown below.

![Salesforce-Selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2633991d-7c45-d377-2b84-cbe05da03448.png)
4. On **Integration Details** popup, fill out the following fields:

| Field | Description |
| --- | --- |
| Instance | Securiti lets you select an instance from the menu. > [!NOTE] > **Important** > > Instances appear in the list only after you configure the third-party **Salesforce** system, enable the **Enable Privacy Platform Integration** toggle, and successfully sync the scopes in [Connectors](https://helpcenter.securiti.ai/docs/connecting-salesforce-securiti-cloud-with-securiti). Securiti then lets you use the objects of this data system in PPI. |
| Integration Name | Enter a suitable name for the integration. |
| Description | Add an appropriate description in the field, such as “Applies predefined consent rules based on country codes for automated compliance decisions”. |
| Integration Direction | Select the **Securiti ← Salesforce** direction to sync consents from the third-party marketing or CRM system such as **Salesforce** to Securiti’s UCM module, as shown below. ![Confirgure-integration-fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1e1efb86-7d28-a8f3-f229-4c3f20c77fa9.png) > [!NOTE] > **Important** > > Proceeding beyond this point finalizes your integration direction. Once set, you can only change the direction by configuring a new integration. |
5. Once done, near the bottom of the popup, click **Save & Continue**, as shown below.

![Save___continue.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fc79f208-e06a-8870-3e39-9fb38868f9a2.png)

Securiti creates your integration and shows you a success message near the upper right corner of the screen, as shown below.

![Suceessful-message.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3d8a6a30-42c5-75f0-5eab-02d1586a3f55.png)
6. On the **Edit Integration** page, fill out the following fields:

| Field | Description |
| --- | --- |
| Object Selection | In the **Primary Object** field, type the name of the primary object or choose a relevant one from the menu, as shown below. ![Primary_Object.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-420a1c86-5cb0-f122-81ce-051087c0c001.png) > [!NOTE] > **Note** > > The **Primary Object** comes from the configured third-party marketing or CRM system such as **Salesforce**, and **Object Selection** holds essential information. It serves as the core for related data organization and actions. |
| User Identifiers (Optional) | The **User Identifiers** section is mapped to the **Unique Subject Identifier (UUID)** feature of UCM. With this, you can: - Choose the **Salesforce Fields** from the menu. - Select **Securiti User ID keys** from the menu, as shown below. ![User_Identifiers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c1344bd3-6381-7e6d-e099-909506bedc4f.png) > [!NOTE] > **Important** > > You must choose appropriate fields for mapping. For instance, if you select `Name` from Salesforce Fields, you must map it to `Name`, or `First Name`, but not to `Mobile Number`. Securiti also lets you add multiple fields in the User Identifiers section. To add a new field, click **+ Add Identifiers**, as shown below. ![Add_Identifiers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b0d8b4de-392e-cada-71cc-42c430037fd8.png) |
| Consents | The Consents section is mapped to the **Processing Purposes** and **Consent Purposes** feature of UCM. With this section, Securiti lets you: - Select the object that represents the combination of processing purposes and consent purposes in **Salesforce Fields**. - Choose the processing purposes and consent purposes from the menu in **Securiti Fields**, as shown below. ![Consents-fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b2a2a9a0-4082-bd9f-fa7b-1822ff4cfcc1.png) For instance, if you have processing purposes named **Product update**, and consent purposes named **SMS** or **Phone**, it means the person has given consent to receive product updates via mobile. - Once you select the field values, you must map them to the corresponding Securiti values. To do this, click **Edit**, as shown below. ![Edit_Consent_Field_Mapping.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8e8a8f8c-475b-3481-2edd-52ec407d536c.png) - From the **Consent Field Mapping** popup, map the **Salesforce field** values to the corresponding Securiti values, and then click **Save**, as shown below. ![Consent_field_mapping-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9220b7ec-c4fd-fe9d-f79c-e70f3f7be81d.png) > [!NOTE] > **Note** > > Mapping values may vary across data systems. For instance, Securiti uses **Granted**, **Declined**, and **No Consent**, while your third-party marketing or CRM systems may use **Yes**, **No**, and **Don’t know**. Securiti also lets you add multiple fields in the **Consents** section. To add a new field, click **+ Add Consent**, as shown below. ![Add_consent.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63aa4a8a-4167-f24d-0c1b-d8a8c4a829e6.png) |
| Other fields | The **Other fields** section is mapped to the **Custom Parameters** feature of UCM. With this, Securiti lets you: - Choose a custom parameter from the menu in **Securiti** **Fields**. - Select appropriate values to map with the custom parameter in UCM under **Salesforce Fields**, as shown below. ![Other_fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-63ab444a-34dd-a455-5291-180136474955.png) Securiti also lets you add multiple fields in the Other fields section. To add a new field, click **+ Add Field**, as shown below. ![Add_fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e52fc098-7503-cd35-03b8-85e0cc0cc943.png) |
| Timestamp & Country | - To configure the **Timestamp** field, you must select the appropriate format from the **Salesforce Fields** menu that matches Salesforce's standard format, as shown below. ![Mapping fields for Timestamp and Country in a data integration interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Timestamp(1).png) - To configure the **Securiti** **Fields** named **Country** with **Salesforce Fields**, select a value from the menu, as shown below. ![Mapping fields for Timestamp and Country in a data integration interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/country.png) - You can map a different country name to ISO Alpha-2, Alpha-3 codes, and the standard country name for inbound operations. For instance, a country like Czechia can be mapped to the Czech Republic to align with the format used in third-party systems. To map a country name: - Access the ​**Country Name Mapping**​ popup from the alert banner under the ​**Timestamp & Country**​​ section, as shown below. ![Instructions for mapping country names and timestamps in a data management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/map_1.png) - From the ​**Country Name Mapping**​ popup, under the ​**Mapping Name**​ column, click ​**Add**​​ (plus icon), as shown below. ![Country name mapping table displaying various countries and their codes, highlighting Afghanistan.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/map_2.png) > [!NOTE] > Important > > - If you already have consent stored in **​Salesforce**​ with a timestamp, lets you preserve that Salesforce standard timestamp in UCM using the ​**Timestamp​​** field. > - **Country**​ and ​**Timestamp**​ are standard fields specific to UCM. The Country field is used to drive consent based on the data subject's location. supports ISO Alpha-2 code, Alpha-3 code, standard country name and mapped country name. |
| [Exceptions](/v1/docs/using-the-rules-matrix) | To map the exceptions defined in the Securiti Fields with the corresponding Salesforce Fields, select the respective values from the menu, as shown below. ![Exceptions_fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e51b8c85-46a3-8eda-170c-298d633e212a.png) Securiti also lets you add multiple fields in the Exceptions section. To add a new field, click **+ Add Field**, as shown below. ![Add_Exceptions__Field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fa696c52-5914-d456-f8f9-dac2b7fc4b88.png) |
| Schedule | In the **Frequency** field under the **Schedule** section, select the time at which syncing occurs based on your needs, as shown below. ![Frequency_field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b2cd1a8b-6c69-f6bd-0900-6ed8a9b0203c.png) For instance, if you select a **15 minute** frequency, the next inbound execution will run after 15 minutes. |
| Mark the Bring all the data in the first time run | - Mark the **Bring all the data in the first time run** checkbox to transfer all consent data the first time the mapping is enabled. On subsequent edits or enablements, Securiti transfers only the delta since the previous run. - Choose the **Date** and **Time** to bring data from Salesforce that was created or updated after the selected timestamp into the Securiti’s UCM module, as shown below. ![Date_time_toggle.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-970cd54b-966b-c5e1-82bb-cf6dc48a3758.png) > [!NOTE] > **Note** > > - By default, the **Date** and **Time** fields take the current date and time if not provided in the integration. > - Once the integration is complete and configured, you can not change the state of this checkbox. |
| Operation Type | In the **Operation type** section, Securiti selects **Update or Insert (Default)** by default. Inbound integration supports only upsert operations. Securiti inserts new consent records but does not update existing ones in UCM, as shown below. ![Operation_Type.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d5f58f3-c308-da23-b0d9-d449ec396e5a.png) |
| Optional Criteria | In the **Optional Criteria** section, specify conditions based on consent field values. Syncing occurs only when the defined criteria are met. Your third-party marketing or CRM systems may store a large amount of data for the selected **Primary Object**. In our case it is `Blackstone__c`, but you may want to import only specific records that meet certain conditions, as shown below. ![Optional_Criteria.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c7c02001-2722-f471-63ea-b890c28acd5b.png) For instance, to integrate data for a specific country, select the **Country (UCM)** field, enter a two-letter country code, and click **Apply**, as shown below. ![optional_criteria_filter.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-24fe6cf7-a9e8-0565-cc2b-07701f72d0fd.png) You can also select multiple values for ​**email​​**, ​**country​​**, ​**names**​​ or other similar text fields. To select multiple values, in the filter criteria panel, below the field name, choose ​**is one of​​** from the menu, as shown below. ![Schedule settings for data syncing with highlighted email property options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_SF_IB_1.png) Type a value, press enter after each additional value, and then click ​**Apply**​​, as shown below. ![Schedule settings with highlighted email fields and options for data synchronization.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_SF_IB_2.png) |
7. Once you complete all fields, click **Save and Continue** at the bottom of the **Edit Integration** tab to save the integration, as shown below.

![Save_and_Continu.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-de171958-2195-3154-5b75-82a4beef3816.png)

> [!WARNING]
> **Caution**
> 
> If you configure **Salesforce Fields** in PPI and later modify or delete them from the Salesforce marketing or CRM system, it may break the integration.
8. Next to the newly created integration, enable **Status** toggle to activate the integration, as shown below.

![_Status_toggle.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5eb28856-e533-bd70-2bf7-a09d78cdbf12.png)

> [!NOTE]
> **Notice**
> 
> You can complete the integration configuration and save your changes before activating the configuration. This lets you iterate and finalize settings before making them active. You can also activate the toggle directly from the **Edit Integration** tab after completing all configurations.
9. From the confirmation popup, click **Yes, Activate**, as shown below.

![Yes__activate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b6865df3-1f85-f894-321f-602afe471a37.png)

Securiti activates the integration and shows a success message near the upper right corner of the screen, as shown below.

![success_message.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-aa10b8e3-355e-e328-3e54-bae92cff0696.png)

Once the integration is activated, Securiti creates a read-only workflow in the background that runs according to the schedule set in the configuration. It generates one workflow for each integration, as shown below.

![wordkflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-660c8182-dac6-2aa9-eca0-9542fea933a0.png)

> [!NOTE]
> **Important**
> 
> Securiti does not let you configure the same field value in multiple sections. For instance, if you configure the email field in the User Identifiers section, you cannot configure the same field in the Consents section.

### Outbound integration of consents from UCM Salesforce

To configure outbound delivery of consent records from UCM to Salesforce:

1. In Securiti, open UCM, and choose **Universal Consent Management > Platform Integrations**.
2. From the upper left corner of the PPI dashboard, click **+ Add Integration**, as shown below.

![Add_Integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b85fbbd6-df48-1aaa-6e19-3bacf34018f7.png)
3. From the **Supports Data Systems** popup, click the **Salesforce** card, as shown below.

![Salesforce-Selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-2633991d-7c45-d377-2b84-cbe05da03448.png)
4. On **Integration Details** popup, fill out the following fields:

| Fields | Description |
| --- | --- |
| Instance | Securiti lets you select an instance from the menu. > [!NOTE] > **Important** > > Instances appear in the list only after you configure the third-party **Salesforce** system and enable the **Enable Privacy Platform Integration** toggle in **Connectors**. Securiti then lets you use the objects of this data system in PPI. |
| Integration Name | Enter a suitable name for the integration. |
| Description | Add an appropriate description in the field, such as “Outbound integration”. |
| Integration Direction | Select the **Securiti → Salesforce** direction to sync consents from Securiti’s UCM module to the third-party marketing or CRM system such as Salesforce, as shown below.![Integration_Direction.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6c72471f-2219-e983-bf1c-a25b94bf163a.png) > [!NOTE] > **Important** > > Proceeding beyond this point finalizes your integration direction. Once set, you can only change the direction by configuring a new integration. |
5. Near the bottom of the popup, click **Save & Continue**, as shown below.

![save___continue.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-355957bd-1c49-23f8-10b8-57439db628ce.png)

Securiti creates your outbound integration and shows you a success message near the upper right corner of the screen, as shown below.

![Success_message.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e973d480-03f7-e739-e49c-662a185566bd.png)
6. On the **Edit Integration** page, fill out the following fields:

| Fields | Description |
| --- | --- |
| Object Selection | In the **Primary Object** field, type the name of the primary object or choose a relevant one from the list, as shown below. ![Object_Selection.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c5aba99d-d3fa-e13c-7d93-eb58f77dc178.png) |
| User Identifiers (Optional) | The **User Identifiers** section is mapped to the UUID feature of UCM. With this section, you can: - Select **Securiti User ID keys** from the menu. - Choose the **Salesforce Fields** from the menu, as shown below. ![User_Identifiers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b0047776-5181-b054-629f-66c2c867166a.png) > [!NOTE] > **Important** > > You must choose appropriate fields for mapping. For instance, if you select `Name` from **Salesforce Fields**, you must map it to `Name`, or `First Name`, but not to `Mobile Number`. Securiti also lets you add multiple fields in the User Identifiers section. To add a new field, click **+ Add Identifiers**, as shown below. ![Add_Identifiers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d0ee6578-a13e-be60-e509-c9df5b32b0e3.png) |
| Consents | This section is primarily for mapping processing purposes and consent purposes configurations with Salesforce fields specific to consent. With this section, Securiti lets you: - Choose the processing purposes and consent purposes from the menu in **Securiti Fields**. - Select the object that represents the combination of processing purposes and consent purposes in **Salesforce Fields**, as shown below. ![Consnet_field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ceb25695-e110-8047-f08b-0868c974bf57.png) For instance, if you have processing purposes named **Product** update and consent purposes named **SMS** or **Phone**, it means the person has given consent to receive product updates via mobile. - Once you select the field values, you must map them to the corresponding values. To do this, click **Edit**, as shown below. ![Add_Consnet_field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d6170901-2602-7685-f0bf-4bcaf8d9d0ae.png) - From the **Consent Field Mapping** popup, map the **Salesforce field** values to the corresponding Securiti values, and click **Save**, as shown below. ![Consent_Field_Mapping-popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-0edb4402-8aa1-3fda-c512-f02ba0af638b.png) > [!NOTE] > **Note** > > Mapping consent values may vary across data systems. For instance, our Securiti’s UCM module uses **Granted**, **Declined**, and **No Consent**, while your data system may use **Opt-in**, **Out-out**, and **None** consent values. Securiti also lets you add multiple fields in the **Consents** section. |
| Other fields | The **Other fields** section is primarily for mapping **Custom Parameters** feature of UCM. With this, You can: - Choose a custom parameter from the menu in **Securiti Fields**. - Select appropriate values to map the custom parameter in **Salesforce Fields** with UCM, as shown below. ![other_fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-32fd3636-abd1-e0cf-1979-67d651708d16.png) Securiti also lets you add multiple fields in the **Other fields** section. To add a new field, click **+ Add fields**, as shown below. ![edit-other_fields.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-7ff2732a-a1c8-9348-e956-816e0a407ebd.png) |
| Timestamp & Country | - To configure the ​**Securiti Fields**​ named ​**Timestamp**​ with ​**Salesforce Fields**​​, choose the value from the menu, as shown below. ![Interface displaying fields for Timestamp, Country, and Consent Status selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ob_timestamp.png) - To configure the ​**Securiti Fields**​ named ​**Country​** with ​**Salesforce Fields**, select a value from the menu, as shown below. ![Configuration options for Timestamp and Country fields in a data management interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/ob_country.png) > [!NOTE] > Note > > Securiti lets you choose the country name format in outbound integrations. You can send country data to third-party systems as ISO Alpha-2 Code, ISO Alpha-3 Code, or as customizable country names, as shown below. > > ![Configuration options for Timestamp and Country fields in a scheduling interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/UCM_outbound.png) |
| Schedule | In **Frequency** field under the **Schedule** section, select the times at which syncing occurs based on your needs, as shown below. ![Frequency_field.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-34241655-883f-6198-e5d6-5aba3381043e.png) For instance, if you select a **15 minute** frequency, the next outbound execution will run after 15 minutes. |
| Mark the Bring all the data in the first time run | - Mark the **Bring all the data in the first time run** checkbox to transfer all consent data the first time the mapping is enabled. On subsequent edits or enablements, Securiti transfers only the delta since the previous run. - Choose the **Date** and **Time** to bring data from **Salesforce** that was created or updated after the selected timestamp into the Securiti data system, as shown below. ![Date_time.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-bb1f4db7-1d5b-da06-a0b0-6da0a253af1a.png) > [!NOTE] > **Note** > > By default, the **Date** and **Time** fields take the current date and time if not provided while adding integration. |
| Operation Type | In the **Operation Type** section, Securiti lets you choose either **Update Only or Update (Default)** or **Insert card**. If Securiti finds matching user identifiers in the third-party system, it updates the records. If no match is found, Securiti creates new ones, as shown below. ![Operation_type.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-4a2bc08f-972a-87dc-391b-3c452813ac38.png) |
| Optional Criteria | In the ​**Optional Criteria**​ section, specify conditions based on consent field values, such as ​**email**​​, ​**Source**​​, ​**Consent Source**​ or ​**Country Code**​​. Syncing occurs only when the defined criteria are met. Securiti’s ​UCM module may store a large amount of data for the selected ​Primary Object​​, but you may want to import only specific records that meet certain conditions, as shown below. ![Optional_Criteria.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-900b7f13-5668-d831-cc24-6825466789e9.png) For instance, to integrate data for a specific email, select the ​​**email​​** field, enter the address, and click ​**Apply**​​, as shown below. ![User interface for scheduling data synchronization with highlighted email property selection.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_OB_CS.png) To select multiple values, in the filter criteria panel, below the field name, select **​is one of​​** from the menu, as shown below. ![Scheduling settings for data synchronization with highlighted email property options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_SF_OB_1.png) Type a value, press enter after each additional value, and then click ​**Apply**​​, as shown below. ![Schedule settings for data synchronization with highlighted email property options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/HC_SF_OB_2.png) |

1. Once you complete all fields, click **Save and Continue** near the bottom of the **Edit Integration** tab to save the integration, as shown below.

![Save_and_Continue.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f7c16425-b1e9-ddac-74ff-ff86694b53b9.png)

> [!WARNING]
> **Caution**
> 
> If you configure Salesforce fields in PPI and later modify or delete them from the Salesforce data system, it may break the integration.
2. Next to the newly created integration, enable **Status** toggle to activate the integration, as shown below.

![Enable_outbound_integration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-affdf6a3-d01f-dcd6-d10f-b377fa0b4911.png)

> [!NOTE]
> **Note**
> 
> You can complete the integration configuration and save your changes before activating the configuration. This lets you iterate and finalize settings before making them active. You can also activate the toggle directly from the **Edit Integration** tab after completing all configurations.
3. From the confirmation popup, click **Yes, Activate**, as shown below.

![Yes__activate.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-8611ae42-d3d4-72a7-c9d0-e7e315762364.png)

Securiti activates the integration and shows a success message near the upper right corner of the screen.

Once the integration is activated, Securiti creates a read-only workflow in the background that runs according to the schedule set in the configuration. It generates one workflow for each integration, as shown below.

> [!NOTE]
> **Important**
> 
> Securiti automatically creates a read-only workflow within its **Workflows** module. This workflow is **immutable** and cannot be **edited** or **modified**. This safeguard is designed to preserve the integrity of all inbound and outbound integrations, ensuring reliable and secure orchestration behavior.

![Workflow.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-48d8b2e0-37cd-6316-7fe8-7324f3eb107c.png)

A system or platform used to manage an organization's interactions with its current and potential customers. CRM systems help organizations store contact data, track communication history, manage sales pipelines, and support customer engagement across various channels such as email, phone, and marketing platforms.

## Related

- [Understanding the Privacy Platform Integrations](/understanding-the-privacy-platform-integrations.md)
- [Configuring Pardot Integration in Securiti](/configuring-pardot-integration-in-securiti.md)
- [Using the Privacy Platform Integrations Runtime Logs](/using-the-privacy-platform-integrations-runtime-logs.md)
- [Using the Privacy Platform Integrations Audit Log](/using-the-privacy-platform-integrations-audit-log.md)
