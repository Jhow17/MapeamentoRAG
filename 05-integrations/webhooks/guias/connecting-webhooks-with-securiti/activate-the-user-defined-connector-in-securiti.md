---
title: "Activate the Webhooks connector in Securiti"
slug: "activate-the-user-defined-connector-in-securiti"
updated: 2026-04-06T07:50:53Z
published: 2026-04-06T07:49:43Z
canonical: "helpcenter.securiti.ai/activate-the-user-defined-connector-in-securiti"
area: integrations
modulo: webhooks
tipo: guia
data_captura: 2026-10-08
---

# Activate the Webhooks connector in Securiti

After you have implemented the necessary API as described in [Implement APIs for the user-defined connector](/latest/docs/implement-apis-for-the-user-defined-connector), activate the user-defined Connector in Securiti:

1. Log in to Securiti with your admin credentials.
2. To open the main menu, from the upper left corner of the left navigation bar, click the **Jewel** icon.
3. From the Platform Services section in new navigation, select **Integrations**.
4. On the **Integrations** page, from the left menu, select **User-Defined**.
5. On the **User-Defined** page, from the upper right corner of the page, click **Add Integration**.
6. From the available data systems page, select **Self Hosted** or **Securiti Hosted** tab and select the **Webhooks Udc** card to connect the aata system directly with Securiti.
7. In the **Basic Information** page, specify the following, and click **Create Instance & Continue**.

| Setting | Description |
| --- | --- |
| Instance Name | Enter a convenient name for the Instance. |
| Instance Location | Choose the country and state, and enter the city where the Instance is located. |
| Owners | Choose additional co-owners for the Instance if you want. By default you are the Instance owner. |
8. On the **Authentication** page, apply the following settings.

| Setting | Authentication type | Description |
| --- | --- | --- |
| Connect with Pod (For self-hosted connector only) | All | For a Self-hosted Connector, select the Pod from menu. |
| Authentication Type | All | From the Authentication menu, choose the Authentication type you configured for the APIs. Your choices are **Basic** and **API Key**. |
| Username | Basic | Enter your API username. |
| Password | Basic | Enter your API password. |
| App Key | API Key | Enter the App Key to be sent in X-API-Key header for API Key based Authentication |
| Polling Target URL | All | In the **Polling Target URL**, enter the URL you configured for the polling API. Usually this is the same URL as the Notification URL |
9. Click **Authenticate and Activate Connector**.

Securiti attempts to connect with your API using the configuration and credentials you configured. If the connection succeeds, the connector status changes to green as shown below. If the test fails, double-check the configuration and API implementation and correct any errors.
10. In the **Configuration** tab, configure the following:
  - (For Self-hosted connector) In the **Privacy** section, mark the **Require indices on primary identifier columns** checkbox to enable automated DSR actions.
  - (For Self-hosted connector) In the **General** section, under **Data Scan Policies** configure the following:

| Setting | Description |
| --- | --- |
| Auto Scan | Mark the checkbox to enable the automatic scan for Webhooks data. |
| Scan Interval | Configure the scan frequency or interval to run scans manually, such as after every 1 month. |
  - In the **General** section, under **Polling Policies** configure the following settings. Polling policies let you control how Securiti polls the target system for responses or status updates after triggering webhook-based workflows.

These settings help you manage timeout behavior, retry attempts, and polling frequency to ensure reliable communication between Securiti and external systems.

| Setting | Description |
| --- | --- |
| Request Timeout | Specify the request timeout value in seconds to define how long Securiti waits for a response from the target system for each polling request. For example, if you set the timeout to 5 seconds, Securiti waits up to 5 seconds for each polling response before marking the attempt as unsuccessful. |
| Poll Interval | Specify the poll interval in minutes. This field controls the delay between consecutive polling attempts. For example, if you set the poll interval to 15 minutes, Securiti checks the status every 15 minutes. |
| Poll Retries | Specify the maximum number of polling attempts Securiti performs if the expected response is not received. |
