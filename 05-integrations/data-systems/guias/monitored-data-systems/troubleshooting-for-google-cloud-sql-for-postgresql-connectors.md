---
title: "Troubleshooting for Google Cloud SQL for PostgreSQL connectors"
slug: "troubleshooting-for-google-cloud-sql-for-postgresql-connectors"
updated: 2025-12-07T08:59:20Z
published: 2025-12-07T08:59:20Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-google-cloud-sql-for-postgresql-connectors"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Google Cloud SQL for PostgreSQL connectors

This topic covers troubleshooting for the possible issues that can occur during Google Cloud SQL for PostgreSQL data system configuration and integration with Securiti.

## Pods connection failure due to Public IPs

If your PostgreSQL instances in Google Cloud Platform (GCP) are configured with Public IPs, the pods must be allowlisted in the database’s network access controls for successful connectivity. When the pod IPs are not allowlisted, the connection attempts fail due to network access restrictions.

To resolve this issue, you can either:

- Update the database instances to use Private IPs, which do not require allowlisting when operating within the same Virtual Private Cloud (VPC).
- Add the Pod's IP address to the allowlist for connections using Public IPs. For more information, see [Google Cloud documentation](https://docs.cloud.google.com/sql/docs/postgres/configure-ip#add).
