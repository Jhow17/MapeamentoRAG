---
title: "Veeam Data Cloud Integration"
slug: "veeam-data-cloud-integration"
updated: 2026-07-16T09:00:37Z
published: 2026-07-16T09:00:37Z
canonical: "helpcenter.securiti.ai/veeam-data-cloud-integration"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Veeam Data Cloud Integration

Veeam Data Cloud (VDC) is a SaaS platform that lets you protect data of multiple cloud platforms using one shared web portal. With VDC, you can start protecting your data without the need to set up and maintain backup infrastructure and software. It provides the benefit of central management of users, subscriptions and all protected workloads of your company.

For more information, see [Veeam Data Cloud Documentation](https://helpcenter.veeam.com/category/vdc.html).

## Obtain credentials in Veeam Data Cloud

Before you can start using Veeam Data Cloud, make sure you have a Veeam account and an active subscription. After your subscription is activated, you will receive an email invitation to your newly created Veeam Data Cloud organization. Follow the link in the invitation to log in to Veeam Data Cloud and start using the service.

1. Log in to [Veeam Data Cloud account](https://dev.cloud.veeam.com/overview) with permissions to create tenants and service accounts.
2. On top right corner of the **Overview** page, click **Settings** icon.
3. From the **Settings** menu, choose **Service Accounts**.

![Overview of Veeam Data Cloud services including Microsoft 365 and AWS backup options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Setting-menu.png)
4. On the **Settings** page, under the **Service Accounts** tab, click **+ Create Service Account**. ![Settings page displaying service accounts with options to create and manage accounts.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/create-button-SC.png)
5. On the **Create Service Account** page, add the following paramters:

| Parameter | Description |
| --- | --- |
| Name | Add the name for the Service Account you want to use for connection with Securiti. |
| (Optional) Description | Add a description for the Service Account. |
| Role | From the Role menu, choose the **OrganizationAdmin** role. |
  - Once you add all the service account parameters, click **Create and Get Secret**. ![Creating a service account with specified name, role, and scope in Veeam Data Cloud.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/add-sc-details.png)
6. On the **Action required: Copy client secret** pop, copy and record the following credentials to use them later for VDC integration in Securiti. Use the following table to understand the credentials format and examples:

| Credential | Example |
| --- | --- |
| Organization ID | `org_12345ABCdef6789` |
| Client ID | `AbC123xYz789LmNoPqRsTuVwXyZ` |
| Client Secret | `XyZ9kLmN0pQrStUvWxYz1234567890AbCdEfGhIjKlMnOpQr` |
  - Once you copy and record all credentials in the following popup, click **Done**. ![Instructions to copy client secret and API credentials for Veeam Data Cloud integration.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Copy-sc-credentials.png)

## Integrate Veeam Data Cloud with Securiti

> [!NOTE]
> Note
> 
> If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

This lets you connect Securiti to your Veeam Data Cloud instance to automate the data discovery, governance, and compliance monitoring across your protected backup workloads.

### Prerequisites

- You must have RBAC permissions to create a VDC integration.
- You have a subscription to VDC instance.
- You have succesfully created a Service Account with Organization admin access in VDC instance, as [outlined above](/latest/docs/veeam-data-cloud-integration#obtain-credentials-in-veeam-data-cloud).

To Integrate your Veeam Data Cloud (VDC) with Securiti, perform the following steps:

1. Log in to Securiti portal.
2. From the left navigation, choose **Settings** > **Integrations** > **Veeam Data Cloud**.
3. On the **Veeam Data Cloud** page, click **Configure Veeam Data Cloud**.
4. On the Veeam Data Cloud configuration page, add the credentials you recorded in [Obtain credentials in Veeam Data Cloud](/latest/docs/veeam-data-cloud-integration#obtain-credentials-in-veeam-data-cloud).

| Parameter | Description |
| --- | --- |
| Organization ID | Enter the Veeam Cloud Organization ID you recorded earlier. See the example below. `org_12345ABCdef6789` |
| Client ID | Enter the Client ID that you recorded earlier for the service account you create in Veeam Data Cloud. See the example below. AbC123xYz789LmNoPqRsTuVwXyZ |
| Client Secret Key | Enter the Client Secret that you recorded earlier for the service account you create in Veeam Data Cloud. See the example below. XyZ9kLmN0pQrStUvWxYz1234567890AbCdEfGhIjKlMnOpQr |
| Environment | From the menu, choose **Production** environment. |
  - Click **Save and authenticate**. It takes you to the following page where you can see the details of successful connection between a Securiti tenant and a VDC instance.

> [!NOTE]
> Note
> 
> Securiti supports only one Veeam Data Cloud integration and maintains one-to-one relationship.

![Veeam Data Cloud settings showing authentication and organization details for data management.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/success-intg.png)

## Verify the integration in Veeam Data Cloud

Once you integrate the Veeam Data Cloud in Securiti, it sends base URL to VDC instance, and confirms the service account credentials work correctly.

To verify the successful integration, perform the following steps:

1. Log in again to your VDC intance.
2. In your VDC instance, choose **Settings** > **Integrations**.
3. On the **Integrations** page, verify the successful integration between your Securiti tenant and VDC Instance. Use the following table to understand the connections details and how to use it.

| Connection element | Description |
| --- | --- |
| Securiti Tenant ID | Shows the ID of Securiti tenant you used to establish a connection with VDC instance. |
| Base URL | Shows the Securiti URL to see the VDC connection and backup data in Securiti’s modules. You can click on this URL to log in to Securiti’s production cloud. |
| Connected on | Shows the time and date on which connection established. |
| Connected by | Shows the VDC service account id which you use for obtaining credentials for Integration. |

![Settings page showing Securiti AI integration details and connection information.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/VDC-integration.png)
4. Proceed to [Connecting to Veeam Data Cloud connector](/latest/docs/vdc-connector).
