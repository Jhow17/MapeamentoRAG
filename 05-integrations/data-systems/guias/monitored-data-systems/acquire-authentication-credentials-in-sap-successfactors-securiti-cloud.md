---
title: "Acquire authentication credentials in SAP SuccessFactors (Securiti Cloud)"
slug: "acquire-authentication-credentials-in-sap-successfactors-securiti-cloud"
updated: 2026-07-30T08:08:15Z
published: 2026-07-30T08:08:15Z
canonical: "helpcenter.securiti.ai/acquire-authentication-credentials-in-sap-successfactors-securiti-cloud"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Acquire authentication credentials in SAP SuccessFactors (Securiti Cloud)

1. Log in to the SAP SuccessFactors Instance and collect the following information:

> [!NOTE]
> **Note**
> 
> This procedure assumes that the User and Password are available prior to Connector Activation.
> 
> SAP SuccessFactors (Self-hosted) Connector uses OAuth 2.0 Authentication using Certificate and API key.
  - **URL** - The datacenter URL of the SAP SuccessFactors Instance.
  - **User** - The username with correct Permissions.

Best to have all read Permissions enabled to fully scan the system for Personally Identifiable Information (PII).
  - **Password** - The user password.
  - **Company ID** - The user's company ID.
2. For the datacenter URL:
  1. Visit the SuccessFactors application URL:

**https://performancemanager8.successfactors.com** OR **https://pmsalesdemo8.successfactors.com**
  2. Notice the integer value in the "<hostname>.successfactors.com".

In the example above, **8** stands for the SAP Instance relating to Data Center 8 (DC8).
  3. Navigate to the following URL:

**https://apps.support.sap.com/sap/support/knowledge/en/2215682**.

It lists datacenter URLs for 3 categories, namely, "Production," "Preview," and "Sales Demo."
  4. On the following page, under **Resolution,** you should see 3 URLs for DC8, as shown below.

![Datacenter-URL.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-6f2c16d3-be77-14e9-8ba0-f4176681151d.png)
  5. Choose a datacenter URL that relates to your application URL, as shown in the Table below.

| Hostnames | Application URL | Datacenter URL |
| --- | --- | --- |
| Sales Demo | https://pmsalesdemo8.successfactors.com | https://apisalesdemo8.successfactors.com |
| Production | https://performancemanager8.successfactors.com | https://api8.successfactors.com |
3. To locate your Company Id:
  1. On the top-right side of the SAP SuccessFactors portal, click your profile picture.

![SAP-SuccessFactors_Portal.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-c744bf8e-7102-a149-c200-60a33435f6f3.png)
  2. On the following menu, select **Show Profile Information**, as shown below.

![Click-Profile-Picture.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-3abe7206-c086-448d-57e6-ab75f4df0341.png)
  3. Copy and save the Company Id, as shown below, for later use.

![Company-Id__1_.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-33297b16-88da-56be-d041-c4bf0f1368ec.png)
4. Proceed to [Connect SAP SuccessFactors (Securiti Cloud) connector with Securiti](/latest/docs/activate-the-sap-successfactors-securiti-cloud-connector-in-securiti).
