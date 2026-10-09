---
title: "Tableau Cloud"
slug: "tableau-cloud-connectors-1"
status: "new"
updated: 2026-06-20T10:53:39Z
published: 2026-06-20T10:54:40Z
canonical: "helpcenter.securiti.ai/tableau-cloud-connectors-1"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Tableau Cloud

Tableau Cloud is a fully-hosted, cloud-based solution that doesn't require any on-premises infrastructure. The solution is designed to empower organizations with intelligent tools and insights where people already work.

Tableau Cloud falls under the [Monitored, Structured](/latest/docs/managing-data-system-connectors) data systems category.

> [!WARNING]
> **Important**
> 
> You must allowlist Tableau URLs for the connector to function correctly.
> 
> - To allowlist the URLs for the Securiti cloud connector, use the below format where instance_id is the Pod name used for activating the connector. https://{{instance_id}}.[online.tableau.com](http://online.tableau.com)

### Connect Tableau Cloud connectors with Securiti

To configure the Tableau connector, perform the following procedures in sequence:

1. [Acquire authentication credentials in Tableau Cloud](/latest/docs/acquire-authentication-credentials-in-tableau-cloud).
2. [Connecting Tableau Cloud with Securiti](/latest/docs/connecting-tableau-cloud-with-securiti).
3. [Initiate Tableau Cloud data scanning](/latest/docs/initiate-tableau-cloud-data-scanning).
4. Do [table training](/v1/docs/table-training-for-structured-and-hybrid-data-systems) for the Tableau data system instance.
