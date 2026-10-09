---
title: "Getting Started with Universal Consent Management"
slug: "getting-started-with-universal-consent-management"
updated: 2026-08-31T09:21:14Z
published: 2026-08-31T09:21:14Z
canonical: "helpcenter.securiti.ai/getting-started-with-universal-consent-management"
stale: true
area: privacy
modulo: universal-consent-management
tipo: guia
data_captura: 2026-10-08
---

# Getting Started with Universal Consent Management

Securiti’s Universal Consent Management module helps you manage consents across various platforms and services. It lets you obtain user permissions for different data processing activities and clearly informs them how their data is used. With the Universal Consent Management module, you can create and manage preference centers where the data subjects can control their consent choices.

[Embedded object](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Universal%20Consent%20Management.drawio.svg)

### Core Offerings

- [Setup Web-based Consent Forms](/latest/docs/getting-started-with-universal-consent-management#setup-webbased-consent-forms)
- [Build Preference Centers](/latest/docs/getting-started-with-universal-consent-management#build-preferences-centers)
- [Upload Consent Records in Bulk](/latest/docs/getting-started-with-universal-consent-management#upload-consent-records-in-bulk)
- [Configure Selective Consent Management](/latest/docs/getting-started-with-universal-consent-management#configure-selective-consent-management)
- [Privacy Platform Integrations](/latest/docs/getting-started-with-universal-consent-management#platform-integrations)
- [Downstream Consent Records via Webhook](/latest/docs/getting-started-with-universal-consent-management#downstream-consent-records-via-webhook)
- [Create a Library of Email Templates](/latest/docs/getting-started-with-universal-consent-management#create-a-library-of-email-templates)
- [Unique Subject Identifier](/latest/docs/getting-started-with-universal-consent-management#unique-subject-identifier)
- [Rules Matrix](/latest/docs/getting-started-with-universal-consent-management#rules-matrix)
- [Workflow Automation](/latest/docs/getting-started-with-universal-consent-management#workflow-automation)

## Setup Web-based Consent Forms

Securiti’s Universal Consent Management module lets you setup web-based consent form(s) through the following steps:

#### Step 1 - Install Browser Plugin

You can install and add Securiti browser plugin to your browsers.

Download the plugin from the following link.

[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti_form_extractor(1).zip)securiti_form_extractor60.59 KB[](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/securiti_form_extractor(1).zip)

With this plugin, you can extract form fields into a JSON object, and then upload it to Securiti to get a code snippet to add to your web form.

[Learn more](/v1/docs/installing-the-browser-plugin)

#### Step 2 - Extract Form Fields in JSON

Securiti lets you extract form fields and buttons from each form, compile them into a JSON object, and then upload this object to Securiti.

[Learn more](/v1/docs/extracting-the-form-json)

#### Step 3 - Import Extracted JSON into Securiti

Once you extract the form JSON, Securiti lets you create a form object within the platform and quickly import the extracted JSON into it for further configuration.

[Learn more](/v1/docs/importing-the-form-json-into-securiti)![import_form_JSON.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f69ed0fd-919e-3d9c-ced8-901eb039964e.png)

#### Step 4 - Generate and Embed Form Consent Code

After successfully importing the form JSON into Securiti, it lets you generate code that you can immediately embed into the form's web page.

[Learn more](/v1/docs/generating-and-embedding-the-form-consent-code)![generate_code.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7e69634-1880-19a7-b9a0-6fdb9b16681b.png)

#### Step 5 - Form Code Testing and Deployment

You can test the form to make sure it accurately reports consent events to the platform. This helps confirm that all consent data is captured correctly and meets compliance standards.

[Learn more](/v1/docs/testing-the-form-code)

### Build Preferences Centers

To build a preference center(s), you first need to make sure the following prerequisites are met:

| ![Processing_Purpose_Thumbnal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-36d8857d-f22e-dfc1-8cf8-0324f07207e5.png) | **Processing Purposes** Securiti lets you configure processing purposes for handling data subject’s personal data. Each form can be associated with a single processing purpose. [Learn more](/v1/docs/configuring-processing-purposes-and-consent-purposes) |
| --- | --- |
| ![Consent_Purpose_Thumbnail.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f87defcf-cfa4-b79c-60fc-6b0060854fc9.png) | **Consent Purposes** You can configure consent purposes for specific actions to which the data subject explicitly consents. [Learn more](/v1/docs/configuring-processing-purposes-and-consent-purposes) |
| ![Processing_Purpose_Categories_Thumbnail_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-efb709e3-dcfb-5bb0-3fd1-1ddeccb2c892.png) | **Processing Purposes Categories** You can build a library of processing purpose categories to map over your collected processing purposes. You can also add them while creating or editing existing processing purposes. [Learn more](/v1/docs/processing-purpose-categories) |
| ![Processing_Purpose_Categories_Thumbnail_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-ae929417-afbb-fd10-d2f1-b7092070ae60.png) | **Map Processing Purposes Categories** You can map processing purpose categories to the relevant processing purposes, making their use more clearer to data subjects. [Learn more](/v1/docs/building-a-universal-preference-center) |

#### Step 1 - Select Template

On the **Select Template** tab, choose the template shown on the UI and click **Template Settings** button to move forward.

[Learn more](/v1/docs/building-a-universal-preference-center)

![Form-template.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8ef2261-c1e4-add8-85e9-cee79072eb1f.png)

#### Step 2 - Configure Template Settings

Securiti lets you select a form style from the available templates to customize your preferences center.

[Learn more](/v1/docs/building-a-universal-preference-center)

![Tempalte-setting.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d92f84c8-2339-b12c-9833-82f0f01dbbd8.png)

#### Step 3 - Configure Preferences Center Access Screen

You can choose theme elements for the page where data subjects fill out the form to receive the one-time URL. You can also customize the background and text colors of the preference center access screen.

[Learn more](/v1/docs/building-a-universal-preference-center)

![Configure_Preference_Center_Access.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c5207e0-5475-76c9-0eb0-b4b925b21f92.png)

#### Step 4 - Tailor Your Preferences Center Content

Securiti lets you customize your preference center content according to your wish.

| ![Location___Language_Intelligence.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a70cbd8d-7eaf-83b9-e288-e0c592a02adc.png) | **Location and Language Intelligence** Securiti lets you create multiple preference centers via the preference center builder for the same region with **Location Intelligence** feature. You can also provide dynamic translation for the preference centers using the **Language Intelligence** feature, based on the language selected by data subjects in their web browser. [Learn more](/v1/docs/location-and-language-intelligence) |
| --- | --- |
| ![Brand_Styling-legal_verbiage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b40baf2a-b3a9-8007-d12a-ea2c181a8be5.png) | **Brand Styling** It lets you update button background color, button text, text color, consent expiration date, configure purposes using the **Purpose Tree** functionality. [Learn more](/v1/docs/building-a-universal-preference-center) |
| ![Opt-in_Configuration.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-37c8df09-292d-c8ca-aa58-26b77e7d2446.png) | **Opt-in Configuration** Securiti lets you build a preference center with the following Opt-in configuration options: - Single Opt-in - [Double Opt-in](/v1/docs/configuring-a-double-opt-in-preference-center) - [Explicit Consent](/v1/docs/configuring-an-explicit-consent-preference-center) You can choose between Single Opt-in for capturing granted or declined consent, Double Opt-in where users must confirm their consent, or the Explicit Consent configuration to comply with various regulations for obtaining explicit consent. [Learn more](/v1/docs/building-a-universal-preference-center) |
| ![Brand_Styling-legal_verbiage.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b40baf2a-b3a9-8007-d12a-ea2c181a8be5.png) | **Legal Verbiage** It lets you update preference center headline text, body text, and button text. [Learn more](/v1/docs/building-a-universal-preference-center) |

#### Step 5 - Configure Email Settings

Securiti lets you choose email templates for your preference center and applies templates to specific preference centers within the Preference Center Builder.

[Learn more](/v1/docs/building-a-universal-preference-center)

![Configure_Email_Settings.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c72a0371-e170-40c7-3d1b-76993506f48b.png)

#### Step 6 - Preview Your Preferences Center

You can preview changes that you make to the preference center configuration in real time from the **Preview** screen on the right side, which renders the changes instantly as you create them. You can also open the preview in a separate browser tab after publishing it.

[Learn more](/v1/docs/building-a-universal-preference-center)

![Preview_Your_Preference_Center.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e1376b68-abb7-51cb-03d2-978b434be39a.png)

#### Step 7 - Publish Your Preferences Center

Once you are satisfied with the configuration of your preference center, Securiti then lets you publish your preference center. You can then copy the hosted link and use it on your website to host the preference center.

[Learn more](/v1/docs/building-a-universal-preference-center)

![Publish_Your_Preference_Center.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b8c951ee-7ef9-f19b-0bab-70bd995b0124.png)

### Platform Integrations

Securiti’s Privacy Platform Integration (PPI) functionality lets you manage consent records across CRM systems like **Salesforce**. You can import ambiguous consent records into Securiti, standardize them using the Rules Matrix, and export accurate consent data back to your CRMs to maintain regulatory compliance.

[Learn more](/v1/docs/configuring-salesforce-integration-in-securiti)

![PPI-dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-5c3bea51-ef27-d599-d6f2-f5d3cb60813e.png)

### Upload Consent Records in Bulk

Securiti lets you import your consent records in bulk directly from the UI via the following formats:

| ![json.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a68c9d0f-9d83-e91e-8afd-55c3733ee4b9.png) | **via JSON** It lets you import your consent records in bulk via JSON format. [Learn more](/v1/docs/consent-uploads-via-ui) |
| --- | --- |
| ![csv.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a356054b-ece8-1fc7-105a-2a6511c43c3f.png) | **via CSV** You can also upload consent records in bulk via CSV format. [Learn more](/v1/docs/consent-uploads-via-ui) |

### Configure Selective Consent Management

| ![Unsubscribe_Success_Page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-fb4f8503-4f1e-cbe4-6444-a1acbe028cf0.png) | **Unsubscribe Success Page** You can configure an unsubscribe success page that lets you send a link to data subjects via email that helps them quickly opt-out (unsubscribe) from their previously given consents. You can add a logo, enable language intelligence, and translation mapping, add headline and body text, preference center button text, and button color. [Learn more](/v1/docs/selective-consent-management) |
| --- | --- |
| ![Resubscribe_Success_Page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a84f46fb-0e3d-a473-9b2c-b5d1fc5fdd8e.png) | **Resubscribe Success Page** You can also configure a resubscribe success page such as you can add logo, enable language intelligence, and translation mapping, add headline and body text, preference center button text, and button color. [Learn more](/v1/docs/selective-consent-management) |

### Unique Subject Identifier

Securiti lets you uniquely identify data subjects with a Unique Subject Identifier setting and improve consent tracking by maintaining a catalog of all UUIDs per organization in one place. It lists your UUIDs for easy access and helps determine the number of UUIDs you are using per organization in your Securiti tenant. It provides two out-of-the-box system UUIDs such as email and uuid, but you can create custom UUIDs as needed.

[Learn more](/v1/docs/using-the-unique-subject-identifier-setting)

![UUIDs_list_page.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-22847a07-37ef-bc54-a9a3-2cf34e5a0285.png)

### Create a Library of Email Templates

Securiti lets you create, configure, and manage email templates for the preference center. You can build a library of email templates to effectively send emails to your data subjects, and enhance communication management.

[Learn more](/v1/docs/customizing-preference-center-email-templates)

![Create_a_Library_of_Email_Templates.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f0de35a3-ee14-deb1-f190-ba93e0bf410a.png)

### Rules Matrix

Securiti lets you use the Rules Matrix functionality to simplify consent compliance and reduce risk. It lets you apply jurisdiction-specific rules to manage communications legally based on compliance type.

[Learn more](/v1/docs/using-the-rules-matrix)

![Rules_Matrix-dashboard.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6e009f1d-657f-b122-cf9f-be523f2bb6be.png)

### Downstream Consent Records via Webhook

Securiti lets you export consent records of your data subjects using the Webhooks Export functionality, which receives 1000 consent records per call in JSON format. It lets you downstream consent records in real-time directly from the Universal Consent Management module to your external platform.

[Learn more](/v1/docs/webhook-export)

![Webhook_Export.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-1d04451c-6ca5-a21d-aab0-ddede6033a89.png)

### Workflow Automation

| Use Case for Consent (Regular) Node |
| --- |
| ![Usecase-1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-86b3d141-1cb3-96e5-e836-8d68a7ef6174.png) | **Triggers Workflow on Desired Time** [Learn more](/v1/docs/cron) The **CRON** trigger node triggers the workflow at the desired time. |
| **Starts Downstreaming Multiple Consent Records** The **Consent** node triggers when you select consent from the specified consent offering in this node. [Learn more](/v1/docs/consent) |
| **Populates Consent Records in Oracle Database** With the **Oracle** node, we populate our consent data records in the database. [Learn more](/v1/docs/oracle) |

| Use Case for Consent Management Trigger Node |
| --- |
| ![Usecase-2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b36da060-d7e2-b80a-8e07-d898d0883f0b.png) | **Triggers and Downstreams One Consent Record** The **Consent Management** trigger node records one consent at a time when we trigger it. [Learn more](https://helpcenter.securiti.ai/latest/docs/en/consent-management-trigger-node) |
| **Populates Consent Record in Oracle Database** With the **Oracle** node, we populate our consent data records in the database. [Learn more](/v1/docs/oracle) |

### Universal Consent Management API Documentation

Securiti offers a set of APIs that let you integrate your preferred platform with ours. The Universal Consent Management API documentation provides detailed descriptions for each API, including information on endpoints and parameters, along with examples and usage guidelines. See the table below for more details:

| **Run APIs directly from the doc** With our interactive API documentation, you can execute API requests directly within the document. This lets you quickly test endpoints, and view API responses without needing to set up a separate environment. [Learn more](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html) | [Embedded content](https://player.vimeo.com/video/1012313059) |
| --- | --- |
| **Download the postman collection** We also provide a Postman collection if you prefer to use it for testing and executing APIs. This collection contains a set of preconfigured requests that let you quickly test and explore the functionalities of our APIs. [Learn more](https://securiti-doc-router.securiti.ai/modules/universal-consent/apidocs/index.html) | ![UCM_APIs.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e0903917-f11d-7b1f-138f-1c82ff9f77b8.png) |

Universally Unique Identifier (UUID) is an alphanumeric string that is used to identify information in computer systems. For instance, they are often used to identify rows of data within a database table, with each row assigned a specific UUID.

## Related

- [Collecting form consent](/collecting-form-consent.md)
- [Building a universal preference center](/building-a-universal-preference-center.md)
- [Consent uploads via UI](/consent-uploads-via-ui.md)
- [Selective consent management](/selective-consent-management.md)
