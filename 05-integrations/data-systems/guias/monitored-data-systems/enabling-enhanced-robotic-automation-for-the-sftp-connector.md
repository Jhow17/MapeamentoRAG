---
title: "Enabling Enhanced Robotic Automation for the SFTP connector"
slug: "enabling-enhanced-robotic-automation-for-the-sftp-connector"
updated: 2025-10-31T06:56:00Z
published: 2025-11-03T07:34:02Z
canonical: "helpcenter.securiti.ai/enabling-enhanced-robotic-automation-for-the-sftp-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Enabling Enhanced Robotic Automation for the SFTP connector

SFTP Data system requires Data Intelligence scanning prior to fulfilling DSR requests. See [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) for more information.

To build the reference list for DSR Automation:

1. Find SFTP in the Data system Connector list to create a new Data system.
2. On the basic information tab, enter Instance Name, Instance Location, Owner, and DSR. See [activating the SFTP connector](/v1/docs/activate-the-sftp-connector-in-securiti) for more information.
3. In the DSR area, mark the **Enable Enhanced Robotic Automation** checkbox, as shown below.

![Enable-RA.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-b892c00a-5d77-e1c2-f18d-8a924decfe1e(1).png)
4. Select **Options > Connect > Initiate Scan**.

Securiti builds a reference list of all objects containing PD and limits it to primary identifiers. These include:

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

For any existing Data system, contact the support team for its implementation. A manual re-scan is required afterward.

> [!NOTE]
> **Note**
> 
> It may take some time to build the reference list.

<style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style><style> p[data-block-id] {font-size:1rem;} ul li p[data-block-id] {margin-bottom: 0;} ul[data-type="taskList"] li div p[data-block-id] {margin-bottom: 0;} ol li p[data-block-id] {margin-bottom: 0;} table tbody th p[data-block-id] { margin-bottom: 0;} blockquote p[data-block-id] {margin-bottom: 0 !important;} &nbsp;p[data-block-id]:empty::after {content: "\00A0";} </style>
