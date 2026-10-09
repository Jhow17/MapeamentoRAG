---
title: "Connecting Collibra with Securiti"
slug: "new-ui-connecting-alation-with-securiti-1"
updated: 2026-10-05T10:19:42Z
published: 2026-10-05T10:19:42Z
canonical: "helpcenter.securiti.ai/new-ui-connecting-alation-with-securiti-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Connecting Collibra with Securiti

This topic covers activation of the Collibra (self-hosted) connector.

## Creating a Collibra data system connector instance

Perform the following steps to create a Data system instance for self**-**hosted connectors:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in the new navigation, select **Integrations**.
4. From the **Integrations** menu, choose **Monitored Data Systems.**
5. On the top right of the **Integrations** page, click **Add Integration** to create a new data system instance.
6. On the Add Integration page, click the **Self-Hosted** tab.
7. From the data system list, choose your Collibra data system.
8. On the **Basic Information** tab, complete the following parameters:

| Parameter | Explanation | Example |
| --- | --- | --- |
| Instance Name | Enter a convenient name for the connector Instance. | Admin-data1 |
| Description | Add a short note to explain the purpose of this instance. | To discover and monitor data sources in the production environment. |
| Hosting Location | Select your preferred **Hosting Location** and configure the Service provider settings where applicable. Securiti supports **SaaS**, or **Private Cloud**, as Hosting options for specific Data system Instances. | SaaS, Private Cloud |
| Country | Select the **country** from the dropdown where the data source or resource is located. | America, Canada |
| (Optional) State | Select the **state** or region from the dropdown within the chosen country. | Alberta |
| (Optional) City | Enter the **city** where the data source or resource is located. | Calgary |
| Owners | Choose **Primary** **Owner** for the Instance. By default, you are the primary owner. | John.doe@securiti.ai |
| (optional) Additional owners can be added after creating an instance by enabling the **Add** **Co-owner** tab on the Basic Information page. From the dropdown, select users to add as additional owners. | Alex.doe@securiti.ai |
| (optional) Enable the toggle for **Send Notification to all Owners** to notify owners. |  |
9. At the Bottom of the page, click **Create and Continue**.

It redirects you to the **Authentication** page.

## Authenticating the Collibra connector

After creating a Collibra connector instance, in the **Authentication** tab, authenticate your connector:

1. Under the **Pod Configuration** section, from the **Select** **Pod** menu, choose the pod you configured earlier.
2. > [!WARNING]
> Important
> 
> - If this feature is not available in your tenant, contact your Customer Success Manager or Account Representative to confirm whether it is included in your plan and whether your tenant meets the eligibility requirements for its activation.

From the **PCS Destination** menu, select one of the configured PCS to store this data system connector's sensitive data, such as:
  - AWS S3
3. In the **Credentials** section, configure the following settings:

| Parameter | Description |
| --- | --- |
| Base URL | The Base URL uses a string value. See example below. *https://collibra-instance.example.com* |
| Username | The Username uses a string value. See example below. *user123* |
| Password | The password associated with the username. It uses a string value. |
4. Click **Test** **Connection** at the bottom of the page.

After you click **Test Connection**, Securiti attempts to reach your Collibra environment using the credentials you provided and shows the result on the same page.

- If the connection test fails, click **Reconfigure** to correct the credentials and run the test again.
- Once the connection test succeeds, click **Continue to Configuration** to configure the supported settings for the connector. This button remains disabled until the connection is established.

1. After the connector is activated, you can use the **Privacy** page to include the instance in your DSR workflow.

To configure the DSR scan:

| Setting | Description |
| --- | --- |
| Guest Users | Enter the email address of each guest user who must act on DSR tasks for this instance, and press **Enter**. Guest users are external collaborators who complete the assigned task without a full Securiti account. |
| Guest User Guidance | The instructions shown to guest users when they open the task. This field is required and is prefilled with default guidance, which you can edit using the rich text editor. |
| Limit Guest access to specific DSR types | Enable this toggle to restrict guest users to selected request types only. When enabled, use the menu below it to choose one or more DSR types, for example **Access**. Leave the toggle disabled to give guest users access to all DSR types. |

  - From the bottom of the page, click **Save**.
  - On the left sidebar of the activated connector, choose **Configuration > Privacy**.
  - Under **DSR Scan**, select the **Include this instance in DSR workflow** checkbox to manage DSR requests for your customers against this instance. Additional settings appear once the checkbox is selected.
  - Configure the following settings:

After the connector is active, open the metadata registration policy, and define the scope in Graph Explorer, then add an action selecting your Collibra connector and map the Securiti attributes to Collibra ones.
