---
title: "Grant permissions and obtain credentials in Salesforce Commerce Cloud"
slug: "grant-permissions-and-obtain-credentials-in-salesforce-commerce-cloud"
updated: 2026-07-31T10:09:49Z
published: 2026-07-31T10:09:49Z
canonical: "helpcenter.securiti.ai/grant-permissions-and-obtain-credentials-in-salesforce-commerce-cloud"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Grant permissions and obtain credentials in Salesforce Commerce Cloud

The Salesforce Commerce Cloud Connector requires the creation of an API Client with “GET”, “POST,” and “DELETE” as minimum Permissions for Activation.

> [!NOTE]
> **Note**
> 
> We assume you have access to the admin account (refer to the procedure [below](/v1/docs/grant-permissions-and-obtain-credentials-in-salesforce-commerce-cloud)) or can contact the Salesforce Commerce Cloud admin to configure Permissions and obtain the parameters required for Connector Activation.

1. Log in to [https://account.demandware.com/dw/account](https://account.demandware.com/dw/account).
2. Grant the following minimum Permissions:
  - GET
  - POST
  - DELETE
3. Record your **Client ID**, **Client Secret**, and **Site ID** from the admin portal.
4. Construct the Base URL by following the steps in the [documentation for Salesforce Commerce Cloud](https://documentation.b2c.commercecloud.salesforce.com/DOC1/index.jsp?topic=%2Fcom.demandware.dochelp%2FOCAPI%2Fcurrent%2Fusage%2FUrlSchema.html).
5. Proceed to [Connect Salesforce Commerce Cloud connector with Securiti](/latest/docs/connecting-salesforce-commerce-cloud-connector-with-securiti).
