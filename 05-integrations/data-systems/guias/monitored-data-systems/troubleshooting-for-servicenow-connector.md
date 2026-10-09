---
title: "Troubleshooting for ServiceNow connector"
slug: "troubleshooting-for-servicenow-connector"
updated: 2026-06-11T15:07:47Z
published: 2026-06-11T15:07:47Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-servicenow-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for ServiceNow connector

This section covers troubleshooting procedures for possible issues that can occur during the ServiceNow connector configuration in Securiti.

In the **Security Posture scan Settings** section on the **General** tab for your Data system Instance, if you see the status message: "Posture scan collection failed", it means that the necessary settings were not configured for your ServiceNow Instance.

Follow the procedure below to resolve the issue.

1. From the main toolbar of your ServiceNow Instance, click **All**.
2. In the search filter, search for the **System Definition** and choose **Tables**.

![servicenow_systemdef.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-f9f8fcf3-a91b-1237-ac46-de13c85ae4e8.png)
3. Choose the **Password Policy** Table and then click the **Application Access** tab.

![servicenow_passwordpolicy.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-17607f64-42fd-b552-da79-c5be0f4f0c60.png)
4. Mark the **Allow access to this Table via web services** check box and click **Update** to save your changes.

![servicenow_posturescan_permission.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-55190fca-4774-94e1-861a-9e3a9a9e0bb7.png)
5. Run Security Posture scan for your ServiceNow Data system Instance in Securiti
