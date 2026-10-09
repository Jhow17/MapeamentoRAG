---
title: "Enabling Enhanced Robotic Automation for Confluence Data Center connector"
slug: "enabling-enhanced-robotic-automation-for-confluence-data-center-connector"
updated: 2025-10-30T19:44:51Z
published: 2025-11-03T06:14:10Z
canonical: "helpcenter.securiti.ai/enabling-enhanced-robotic-automation-for-confluence-data-center-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Enabling Enhanced Robotic Automation for Confluence Data Center connector

The Confluence Data Center data system requires Data Intelligence scanning before fulfilling DSR requests. See [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) for more information.

To build the reference list for DSR Automation:

1. Find Confluence Data Center in the data system connector list to create a new data system.
2. On the basic information tab, enter Instance Name, Instance Location, Owners, and DSR. See [activating the Confluence Data Center connector](/v1/docs/activate-the-confluence-data-center-connector-in-securiti) for more information.
3. In the DSR area, mark the **Enable Enhanced Robotic Automation** checkbox, as shown below.

![DSR_area.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7be57c5-996f-b947-e279-47b857339387.png)
4. On the connector tab, click **Initiate Data Scan** once you've activated the connector and it finishes learning under "Data Scan Policies."

> [!NOTE]
> **Important**
> 
> Any data system with discovery scan support shows the **Create Discovery Scan** button on the connector tab instead of Initiate Data Scan.

> [!NOTE]
> **Note**
> 
> (Optional) Mark the **Scan for Primary Data Elements checkbox only** if you want the scan to discover primary PDs.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(632).png)

Securiti builds a reference list of all PD objects and limits it to primary identifiers. These include:

- "Username"
- "Email"
- "Passport Number"
- "Driver License Number"
- "US SSN"
- "TSA Precheck Number"
- "US Tax Payer ID"
- "US DoD ID Number"
- "US VISA Number"
- "US Alien Registration Number"
- "IN Aadhaar Card Number"
- "IN PAN Number"
- "BR CPF"
- "AU Medicare Number"
- "AU Tax File Number"
- "NZ NHI"
- "MRN"

For any existing data system, contact the support team for its implementation. A manual re-scan is required afterward.

> [!NOTE]
> **Note**
> 
> It may take some time to build the reference list.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
