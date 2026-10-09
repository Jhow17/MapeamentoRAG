---
title: "Troubleshooting for Microsoft SQL Server connector"
slug: "troubleshooting-for-microsoft-sql-server-connector"
updated: 2026-06-18T08:06:21Z
published: 2026-06-18T08:06:21Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-microsoft-sql-server-connector"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for Microsoft SQL Server connector

This document covers troubleshooting possible issues during Microsoft SQL Server Authentication and Configuration.

If you're facing issues with Kerberos Authentication in SQL Server when using the krb5.conf Configuration file, we recommend you manually specify the realm, KDC, and service principal without the Configuration file when reconfiguring the Connector.

If you see this error, "Kerberos Login failed: Integrated Authentication failed.", you must verify your `krb5.conf` Configuration file for the following:

- Ensure the file includes the correct realm and KDC (Key Distribution Center).
- Ensure the file does not contain any parameters or encryption types that Securiti does not support.

Remove any unsupported parameters and authenticate the Connector again. See an example below of some parameters that Securiti does not support.

```plaintext
rdns = false
pkiinit_anchors = FILE:/etc/pki/tls/certs/ca-bundle.crt
spake_preauth_groups = edwards25519
default_ccache_name = KEYRING:persistent:%{uid}
default_tgs_enctypes = aes256-cts-hmac-sha512-256, aes256-cts-hmac-sha256-128
default_tkt_enctypes = aes256-cts-hmac-sha512-256, aes256-cts-hmac-sha256-128
permitted_enctypes = aes256-cts-hmac-sha512-256, aes256-cts-hmac-sha256-128
```

We recommend that you use the format described in [Microsoft's documentation](https://learn.microsoft.com/en-us/sql/connect/jdbc/using-kerberos-integrated-authentication-to-connect-to-sql-server?view=sql-server-ver16#creating-a-kerberos-configuration-file) as shown below:

```plaintext
[libdefaults]
default_realm = YYYY.CORP.CONTOSO.COM
dns_lookup_realm = false
dns_lookup_kdc = true
ticket_lifetime = 24h
forwardable = yes

[domain_realm]
.yyyy.corp.contoso.com = YYYY.CORP.CONTOSO.COM
.zzzz.corp.contoso.com = ZZZZ.CORP.CONTOSO.COM

[realms]
YYYY.CORP.CONTOSO.COM = {
  kdc = krbtgt/YYYY.CORP.CONTOSO.COM @ YYYY.CORP.CONTOSO.COM
  default_domain = YYYY.CORP.CONTOSO.COM
}
```

### Using the diagnostic report to resolve authentication failures

When the SQL Server connector fails to authenticate or activate, Securiti runs a comprehensive diagnostic report that pinpoints which step failed and why. Use the tables below to identify the failure and resolve it based on your authentication method.

> [!NOTE]
> **Note**
> 
> The diagnostic report runs automatically after connector activation or reconfiguration. A failed diagnostic step does not always mean authentication failed. The report validates all connector operations, not just authentication. For more information, see [Auto-diagnostic reports in data system connectors](/latest/docs/auto-diagnostic-reports-in-data-system-connectors).

#### SQL authentication

| Symptom | Diagnostic step | Resolution |
| --- | --- | --- |
| Connector activates but cannot reach the database | Connectivity check | Verify the host IP address and port are correct and accessible from the pod. |
| Authentication fails immediately | Credentials check | Verify the username and password. Ensure the SQL Server account is not locked. |
| Database name not found | Database access check | Confirm the database name is correct and case-sensitive. Verify the service account has access to the database. |
| Scan returns no results | Data prep check | Confirm the database contains tables. If no tables exist, Securiti cannot run a discovery scan. |
| Scan fails with permission error | Permissions check | Grant the service account SELECT permissions on tables and access to constraints. For more information, see [Prerequisites for Microsoft SQL Server connector](/latest/docs/prerequisites-for-microsoft-sql-server-connector). |

#### Kerberos authentication

| Symptom | Diagnostic step | Resolution |
| --- | --- | --- |
| Cannot reach the KDC | KDC connectivity check | Verify the KDC IP address and Kerberos realm are correct. Ensure UDP port 88 is open between the pod and the KDC. |
| Invalid SPN error | Authentication check | Verify the Service Principal Name (SPN) is registered correctly in Active Directory. For more information, see [Prerequisites for Microsoft SQL Server connector](/latest/docs/prerequisites-for-microsoft-sql-server-connector). |
| Unknown host or invalid port | Connectivity check | Verify the host address and port. Ensure DNS resolves the host from the pod network. |
| Invalid KDC or realm | KDC connectivity check | Check your `krb5.conf` file for unsupported parameters or incorrect realm values. For supported formats, see the Kerberos configuration section above. |

#### Windows authentication

| Symptom | Diagnostic step | Resolution |
| --- | --- | --- |
| Connection refused by host | Connectivity check | Verify the public and private IP addresses are configured correctly. Ensure the Windows host is reachable from the pod. For more information, see [Prerequisites for Microsoft SQL Server connector](/latest/docs/prerequisites-for-microsoft-sql-server-connector). |

#### Azure AD authentication

| Symptom | Diagnostic step | Resolution |
| --- | --- | --- |
| Authentication fails | Credentials check | Verify the Azure AD username and password. Ensure the account has not expired or been disabled in Azure. |
| Database not found | Database access check | Confirm the database name is spelled correctly and the Azure AD account has access to it. |
| Invalid host or port | Connectivity check | Verify the SQL Server endpoint is reachable and that the correct JDBC driver for Azure AD is uploaded. For more information, see [Downloading JDBC drivers for SQL connectors](/latest/docs/downloading-jdbc-drivers-for-sql-connectors). |
| Metadata syncs but scan fails | Permissions check | Grant the Azure AD account SELECT permissions on all tables you want to scan. |
