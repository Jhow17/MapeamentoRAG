---
title: "Configuring identity verification with Unico"
slug: "configuring-identity-verification-with-unico"
updated: 2025-10-30T19:20:04Z
published: 2025-11-03T07:39:28Z
canonical: "helpcenter.securiti.ai/configuring-identity-verification-with-unico"
area: privacy
modulo: data-subject-rights
tipo: guia
data_captura: 2026-10-08
---

# Configuring identity verification with Unico

You can configure Securiti to use Unico (formerly Acesso Digital) as an identification verification feature for DSR requests. Unico is an Identity verification provider in Brazil used by many large retailers. It provides identity verification services using the data subject’s CPF and a selfie photo.

After you configure this feature, Securiti verifies data subject identities as described for Unico in [How Securiti verifies data subject identity](/v1/docs/how-securiti-verifies-data-subject-identity).

In order to use this feature:

- You must request an Unico service account as described here:

[https://acesso-io.github.io/docs/platform/identity/protocols/oauth2/service-account.html](/v1/docs/optional-connect-using-another-service-account)

When Unico creates your service account, they send you information about generating the key pair you will need later. Collect the following information to configure in Securiti :
  - Service Account Name
  - Tenant Identifier
  - Enterprise Name
  - API Key
  - API Secret
- You must contact your Securiti representative to activate this feature for your Securiti account.

> [!NOTE]
> **Note**
> 
> For all the errors raised by Unico except id verification failure we request that the user retry.

Once we have activated this feature for your Securiti account, use the following procedures to configure it:

### Configure the Unico instance in Securiti

1. In Securiti choose **Data Subject Rights > Settings > Identity Verification**, and for Unico click **View Instances** then click **Create Instance**.
2. Near the upper right corner of the page click **Edit**, then fill in the information you collected from Unico as shown below.

| Setting | Description |
| --- | --- |
| Instance Name | Enter a descriptive name for the instance. |
| Service Account | Enter the Service Account Name you received from Unico. |
| Tenant Identifier | Enter the Tenant Identifier you received from Unico. |
| Enterprise Name | Enter the Enterprise Name you received from Unico. |
| Enterprise Name | Enter the Enterprise Name you received from Unico. |
| API Secret | Click the paperclip icon and load the .PEM file for the API secret you received from Unico. |

![RN_IDV_1.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-e773f0a3-612a-f5b4-0982-9be56bc91de0.png)
3. Click **Test And Activate** to validate the settings.

### Collect information in Securiti.

1. In Securiti, click **Settings** and on the General page record the value for Tenant as shown below to use later.

![Collect_tenant_ID.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b3cc07af-133f-eed4-7351-9224a6c8cb16.png)
2. Choose **Integrations > Credentials > API Keys**.
3. Near the upper right corner of the page, click **Generate API Key**.
4. On the Generate API Key popup, choose **DSR**, then click **Generate**.
5. On the API Key Details popup:

![Securiti_API_Key_Details_popup.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-cebf46be-882e-a459-05aa-f90ee75e8038.png)
  1. Enter a name and description for the API key.
  2. Record the API Key and API Key Secret to use later.
  3. Click **Save**.

### Configure Securiti in Unico

1. Login to the Unico admin console.
2. Near the upper left corner of the page, click the menu icon and choose **Configurações > Integração > Webhook**.
3. On the Webhooks page, click **+ Novo Webhook**.
4. Apply the following settings, as shown below:

| Setting | Description |
| --- | --- |
| Descrição | Enter a description of the webhook. |
| Request URI | US Cloud | https://privacy-central.securiti.ai/integration/v1/request-submission/unico-response |
| EU Cloud | https://privacy-central.eu.securiti.ai/integration/v1/request-submission/unico-response |
| Status | Ativo |
| Notificar alterações de score suspeito | Não |
| Tempo entre tentativa em minutos | 3 |
| Número máximo de tentativas | 5 |
| Secret | Leave blank |
| Tipo de autenticação | Nenhuma |

![Add_new_webhook.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-9590cab4-e6ea-721e-4e97-866c739d0a13.png)
5. Click **+ Adicionar** four times to add four headers.
6. Apply the following header settings, as shown below:

| Header | Value |
| --- | --- |
| X-TIDENT | Enter the Securiti tenant identifier you recorded on the Securiti Settings > General page . |
| X-API-KEY | Enter the API Key you generated in Securiti. |
| X-API-SECRET | Enter the API Secret you generated in Securiti. |
| USER-AGENT | **UNICOSERVER** |

![Webhook_add_headers.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-190c2995-8f8f-b883-455c-3bc8895c76c1.png)
7. Click **Salvar**.
8. Near the upper left corner of the page, click the menu icon and choose **Configurações > Integração > API Key**.
9. If you have more than one API key, click the key you want to use for Securiti.
10. From the Webhook menu, choose the webhook you just created, as shown below.

![API_key_webhook.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b7eb0990-38d6-d0e3-9cab-1e94482cc493.png)
11. Click **Salvar**.

### Configure your DSR forms to use Unico for identity verification

After configuring the Unico instance, you next configure your DSR forms to use ID verification by Unico and also to collect the necessary Brazil CPF.

1. In Securiti, open **Data Subject Rights** and choose **Settings > Form Builder**.
2. Choose the form you want to use, or create a new one.
3. On the Form Settings tab, mark the checkbox for **External ID verification** and choose **Unico** as the ID verification service as shown below.

![RN_IDV_2.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-84217ccc-5601-a131-3893-b6c143043a48.png)
4. On the Customize Content tab, in the Define Form Fields and Requirements area, find the Phone Number component and near its upper right corner click **Edit**.
5. Scroll down to the Input Mask area and set the input mask to **55(99)99999-9999** as shown below.

![Unico_phone_number_mask.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-03d2bbfd-3a8f-0fed-e435-6fdf7895019b.png)
6. On the Validation tab, mark the checkbox for **Required** as shown below.

![Unico_phone_number_valid_required.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-de90abc4-d27f-8748-89c8-f76d09d61e6a.png)
7. On the Customize Content tab, add a new custom field of type “text field” onto the form.
8. On the Text Field Component popup Display tab, give it the label “CPF” or similar and set the Input Mask to **999.999.999-99** as shown below.

![RN_IDV_3.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-73307dd8-7da8-1a94-3b80-0b9f47c796d8.png)

![RN_IDV_3_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b33c6e22-99e6-5c9a-ddec-7796ef3a0e24.png)
9. On the API tab, set the Property Name to **cpf_brazil** as shown below.

![RN_IDV_4.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-d5009a5b-8741-6db2-528e-b2d3ed9dc4a4.png)
10. On the Validation tab, mark the checkbox for **Required** as shown below.

![RN_IDV_5.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b12aae19-8136-c815-bfcc-410a4ba0d301.png)
11. On the Identity Profile tab, mark the checkbox for **Identity PD**, and for PD Attribute choose **BR CPF** as shown below. Then click **Save** to save the new custom field for CPF.

![RN_IDV_6.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-95e00cbd-27a9-0bb4-c463-a4ac189826b1.png)
12. Click **Review & Publish** and then click **Publish** to publish the DSR request form.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>

## Related

- [How Securiti verifies data subject identity](/how-securiti-verifies-data-subject-identity.md)
