---
title: "Acquire authentication credentials in SAP SuccessFactors (Self-Hosted)"
slug: "acquire-authentication-credentials-in-sap-successfactors-self-hosted"
updated: 2026-07-30T06:51:02Z
published: 2026-07-30T06:51:02Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-sap-successfactors-self-hosted"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in SAP SuccessFactors (Self-Hosted)

1. Log in to the SAP SuccessFactors Instance and collect the following information:

> [!NOTE]
> **Note**
> 
> - This procedure assumes that the User, API Key, and Private key file are available prior to Connector Activation.
> - SAP SuccessFactors (Self-hosted) Connector uses OAuth 2.0 Authentication using Certificate and API key.

| Parameter | Description |
| --- | --- |
| URL | The datacenter URL of the SAP SuccessFactors Instance. Refer to the step below for more information. |
| User | The username with correct Permissions. It is best to have all read Permissions enabled to fully scan the system for Personally Identifiable Information (PII). |
| API key | API key generated and assigned to Securiti after registering for OAuth 2.0 Authentication with the Connector. |
| Company ID | Your company ID in SAP SuccessFactors portal. |
| Private key file | Certificate (.pem) file corresponding to private key. |
2. For the datacenter URL:
  1. Visit the SuccessFactors application URL:

**https://performancemanager8.successfactors.com** OR **https://pmsalesdemo8.successfactors.com**
  2. Notice the integer value in the "<hostname>.successfactors.com".

In the example above, **8** stands for the SAP Instance relating to Data Center 8 (DC8).
  3. Navigate to the following URL:

**https://apps.support.sap.com/sap/support/knowledge/en/2215682**.

It lists datacenter URLs for 3 categories, namely, "Production," "Preview," and "Sales Demo."
  4. On the following page, under **Resolution,** you should see 3 URLs for DC8, as shown below.

![Datacenter-URL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f2c16d3-be77-14e9-8ba0-f4176681151d(1).png)
  5. Choose a datacenter URL that relates to your application URL, as shown in the Table below.

| Hostnames | Application URL | Datacenter URL |
| --- | --- | --- |
| Sales Demo | https://pmsalesdemo8.successfactors.com | https://apisalesdemo8.successfactors.com |
| Production | https://performancemanager8.successfactors.com | https://api8.successfactors.com |
3. To locate your Company ID:
  1. On the top-right side of the SAP SuccessFactors portal, click your profile picture.

![SAP-SuccessFactors_Portal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c744bf8e-7102-a149-c200-60a33435f6f3(1).png)
  2. On the following menu, select **Show Profile Information**, as shown below.

![Click-Profile-Picture.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3abe7206-c086-448d-57e6-ab75f4df0341(1).png)
  3. Copy and save the Company ID for later use.
4. Proceed to [Connect SAP SuccessFactors (Self-Hosted) connector with Securiti](/latest/docs/activate-the-sap-successfactors-self-hosted-connector-in-securiti).
