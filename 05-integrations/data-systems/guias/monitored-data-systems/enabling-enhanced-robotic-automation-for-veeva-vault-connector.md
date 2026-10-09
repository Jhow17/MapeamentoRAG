---
title: "Enabling Enhanced Robotic Automation for Veeva Vault connector"
slug: "enabling-enhanced-robotic-automation-for-veeva-vault-connector"
updated: 2025-12-11T13:54:48Z
published: 2025-12-11T13:54:48Z
canonical: "helpcenter.securiti.ai/enabling-enhanced-robotic-automation-for-veeva-vault-connector"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Enabling Enhanced Robotic Automation for Veeva Vault connector

The Veeva Vault Data system requires Data Intelligence scanning before fulfilling DSR requests. See [Sensitive Data Intelligence](/v1/docs/using-sensitive-data-intelligence) for more information.

To build the reference list for DSR Automation:

1. Find Veeva Vault in the Data system Connector list to create a new Data system.
2. On the basic information tab, enter Instance Name, Instance Location, Owners, and DSR. See [activating the Veeva Vault connector](/v1/docs/activate-the-veeva-vault-connector-in-securiti) for more information.
3. In the DSR area, mark the **Enable Enhanced Robotic Automation** checkbox, as shown below.

![DSR_area.png](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/uuid-a7be57c5-996f-b947-e279-47b857339387(2).png)
4. On the Connector tab, click **Initiate Data scan** once you've activated the Connector and it finishes Learning under "Data scan Policies."

> [!WARNING]
> **Important**
> 
> Any Data system with Discovery scan support shows the **Create Discovery scan** button on the Connector tab instead of Initiate Data scan.

> [!NOTE]
> **Note**
> 
> (Optional) Mark the **Scan for Primary Data Elements checkbox only** if you want the scan to discover primary PDs.
> 
> ![](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/image(617).png)

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

For any existing Data system, contact the support team for its implementation. A manual re-scan is required afterward.

> [!NOTE]
> **Note**
> 
> It may take some time to build the reference list.
