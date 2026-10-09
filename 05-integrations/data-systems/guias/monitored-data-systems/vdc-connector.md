---
title: "Connecting to Veeam Data Cloud"
slug: "vdc-connector"
updated: 2026-05-10T11:00:46Z
published: 2026-05-10T11:00:46Z
canonical: "helpcenter.securiti.ai/vdc-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting to Veeam Data Cloud

## Prerequisites

- You must enable New Integration UI for your Securiti tenant.
- > [!NOTE]
> Note
> 
> If Databricks Migration is not complete for your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.
- You must integrate VDC instance with your Securiti tenant. For more information, see [Veeam Data Cloud integration](/latest/docs/veeam-data-cloud-integration).

> [!NOTE]
> Note
> 
> If Veeam Data Cloud integration is for your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

This topic covers activation of the VDC Securiti Cloud connector.

## Creating a data system instance

Perform the following steps to create a Data system instance for Securiti cloud connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Securiti-Cloud** tab.
7. From the data system list, choose your relevant data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, **or** **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating with Veeam Data Cloud

After creating a VDC for M365 instance, perform the following steps:

1. On the **Authentication** tab, under the **Credentials** section, verify the prepopulated VDC Org ID. This organization ID appears from the VDC integration you configured in the following topic. VDC Org ID follows the following format. `org-1ab01AbC001A345`
2. Click **Test Connection**. Wait until authentication process verifies the VDC integration details, and completes the learning of all tenants in the available organization. ![VDC Connector interface showing connection test and authentication settings options.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/vdc-connector-waiit-screen.png)
  - Once authentication is complete, you see the following page. ![Status shows scan completed, authentication finished, ready to initiate data scan.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/VDC-connector-success.png)
3. Proceed to [Initiate data scanning for VDC M365](/latest/docs/initiate-data-scanning-for-vdc-for-m365-connector).
