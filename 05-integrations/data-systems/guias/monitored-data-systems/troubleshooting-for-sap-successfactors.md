---
title: "Troubleshooting for SAP SuccessFactors"
slug: "troubleshooting-for-sap-successfactors"
updated: 2026-04-07T03:50:53Z
published: 2026-04-07T03:50:53Z
canonical: "helpcenter.securiti.ai/troubleshooting-for-sap-successfactors"
stale: true
area: integrations
modulo: data-systems
tipo: guia
data_captura: 2026-10-06
---

# Troubleshooting for SAP SuccessFactors

This page covers the troubleshooting guide for SAP SuccessFactors authentication and access errors.

### 1. Failed SAP SuccessFactor authentication

You will see the following error message:

```plaintext
"No such file or directory – Failed to open SAP SuccessFactors connection."
```

#### Description

You see the above-mentioned error because the default `OAuthSettingsLocation` path is not accessible.

#### Resolution

To resolve the above error:

1. In the **Authentication** section, click **Reconfigure**.
2. In the **Additional Connection String Options**, Type `OAuthSettingsLocation=memory://sap_sf_oauth`.
3. Click **Save Configuration and Continue**.

### 2. Failed SAP SuccessFactor authentication

You will see the following error message:

```plaintext
jdbc proxy request failed due to err : rpc error: code = Internal desc = class java.sql.SQLException,Error message =PrivateKey connection property is required for OAuthGrantType=SAML.
```

#### Description

You see the above-mentioned error because the private key used for connector authentication is invalid

#### Resolution

To resolve the above error:

1. In the **Authentication** section, click **Reconfigure**.
2. In the **Private Key**, verify that the `.pem` file is valid and the `.pem` file is expected to contain only the key and not the certificate.
3. Click **Save Configuration and Continue**.
