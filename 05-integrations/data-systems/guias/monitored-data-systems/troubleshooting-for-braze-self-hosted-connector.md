---
title: "Troubleshooting for Braze (self-hosted) connector"
slug: "troubleshooting-for-braze-self-hosted-connector"
updated: 2025-10-30T19:31:48Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-braze-self-hosted-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Braze (self-hosted) connector

This section covers troubleshooting for the following issues when configuring Braze data system connector.

#### No data in discovery scan results

Verify the following in case the Braze discovery scan results in no data scanned.

- Check if the Braze instance is connected to any Cloud Storage Platform by following these steps on the Braze Portal:
  1. Navigate to **Integrations**
  2. Select **Technology Partners**
  3. See if any cloud storage platform is integrated to your instance. If your Braze instance is connected to any cloud storage other than Amazon S3, discovery scan will fail as integration with Amazon S3 is supported only.
- Check if you have selected the right **Target Data System** in the **Connector** tab, during the connector activation process. Select **AWS S3** if your instance is integrated to Amazon S3 cloud storage otherwise, select **Default**.
- Check if **Default** is selected in the **Target Data System** field in the **Connector** tab while your instance is integrated with Amazon S3. In this case, you must reactivate your connector and select **AWS S3**.

![braze_targetds.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-485f5fca-0ae8-9d63-81b3-727d795ee4a3(1).png)

See [Prerequisites for Braze (self-hosted) connector](/v1/docs/prerequisites-for-braze-self-hosted-connector) for more information.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
