---
title: "Troubleshooting for Databricks"
slug: "troubleshooting-for-databricks"
updated: 2025-12-06T15:01:44Z
published: 2025-12-06T15:01:44Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-databricks"
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Databricks

This page covers the troubleshooting guide for Databricks authentication and connection errors.

## Databricks JDBC connection and access errors

These Databricks JDBC errors indicate failed communication between your cluster and the Databricks workspace. They commonly occur due to restricted network access, invalid or expired authentication tokens, or misconfigured connection parameters. A 403 (Forbidden) response means the connection reached Databricks but was blocked by access controls.

You can see the following errors:

- ```plaintext
Error: [Databricks][JDBCDriver](500593) Communication link failure. Failed to connect to server. Reason: HTTP Response code: 403, Error message: Invalid access to Org: 4625866504375480.
```
- ```plaintext
Error: [Databricks][JDBCDriver](500593) Communication link failure. Failed to connect to server. Reason: HTTP Response code: 403, Error message: Unknown.
```
- ```plaintext
Error: [Databricks][JDBCDriver](500593) Communication link failure. Failed to connect to server. Reason: HTTP Response code: 403, Error message: Unauthorized network access to workspace: 4625866504375480.
```
- ```plaintext
Error message =[Databricks][JDBCDriver](500004) Error getting schema information: Metadata Initialization Error.
```

To resolve the above errors, perform the following steps:

1. **Allow network access:** Ensure all cluster nodes can reach the Databricks host by updating outbound firewall rules.
  1. Edit the `resolved.conf` file:

```plaintext
sudo nano /etc/systemd/resolved.conf
```
  2. Set the Domain Name Servers (DNS).
  3. Save the configurations.
  4. Restart the systemd-resolved service.

```plaintext
sudo systemctl restart systemd-resolved
```
  5. Verify DNS configuration.

```plaintext
resolvectl status
```
2. **Update connection string:** Add `AuthMech=3` to the Additional Connection String parameters.
3. **Enable SSL:** Set Use SSL to true.
4. **Validate authentication:** Check if the token has expired, for instance, test it using DBeaver.
5. **Allowlist source IPs:** Verify that all node IPs (POD IPs) are included in your Databricks workspace allowlist.
