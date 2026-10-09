---
title: "Troubleshooting for Salesforce"
slug: "troubleshooting-for-salesforce-legacy-and-cloud-connectors"
updated: 2026-03-03T07:17:56Z
published: 2025-11-03T07:38:02Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-salesforce-legacy-and-cloud-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Salesforce

## Expired access or refresh token erro

In case you face any of the below errors.

- "Refresh Token doesn’t exist in postgres”
- “oauth2: invalid_grant expired access/refresh Token”

You must reconfigure the Connector to resolve the issue, as the refresh Token expires if there are 5 more access Token calls made after activating the Connector.
