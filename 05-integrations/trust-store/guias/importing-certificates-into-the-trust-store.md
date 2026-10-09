---
title: "Importing certificates into the Trust Store"
slug: "importing-certificates-into-the-trust-store"
updated: 2026-04-06T09:34:55Z
published: 2026-04-06T09:34:55Z
canonical: "helpcenter.securiti.ai/importing-certificates-into-the-trust-store"
area: integrations
modulo: trust-store
tipo: guia
data_captura: 2026-10-08
---

# Importing certificates into the Trust Store

> [!NOTE]
> **Note**
> 
> Importing a Certificate is required when you want to make an SSL Connection during Connector Activation.

Securiti lets you import the **Certificate Authority (CA)** certificates, which are essential for establishing a secure and trusted Connection with data systems that use SSL certificates signed by those CAs. This enables Securiti's data connectors to verify the server's identity and ensures that all communication between Securiti's Connector and then Data system is encrypted and protected against eavesdropping or tampering.

### Format and content of certificates

The Certificate must be in **Standard X.509** format and is usually provided as a **.pem** or **.crt** file

The content of the Certificate files follows the following format:

```plaintext
-----BEGIN CERTIFICATE-----
<Certificate Key>
-----END CERTIFICATE-----
```

### No import required for widely trusted certificates

You don’t need to import a CA Certificate if the server's Certificate is signed by a widely recognized and globally trusted CA, such as:

- Let's Encrypt
- DigiCert
- GlobalSign
- Sectigo, etc.

> [!NOTE]
> **Important**
> 
> Such well-known CAs are typically trusted by default by operating systems and applications. Note that the above list is not exhaustive. However, in some advanced or specific network configurations, you might be required to import even a well-known CA Certificate.

### When to import a certificate?

You typically upload a CA Certificate if the Data system you are connecting to uses one of the following certificates:

| Certificate type | Explanation |
| --- | --- |
| Self-signed Certificate | It means the server or Data system has generated its security Certificate, which hasn't been verified by a widely recognized authority. Uploading the server’s CA Certificate here explicitly tells Securiti's application to trust it. |
| Certificate from a custom or private CA | Some organizations or less common Certificate providers issue their own certificates. If the server or Data system uses one of these, you must upload the Certificate of the issuing private certified authority here. |

### How to import?

To import the CA Certificate:

1. In Securiti, on the left navigation, choose **Integrations > Trust Store**. ![Securiti interface showing integrations with highlighted Trust Store option and data systems.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Trust-store-navigation.png)
2. On the **Trust Store** page, click **+ Import CA Certificate**.

The Certificate must be in Standard X509 format with the below outline.

![Overview of certificate management with valid and expired certificates listed in the interface.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Certificates-list.png)
3. On the **Upload** popup:
  - Drag and drop the `.pem` or `.crt` file into the designated area, or
  - Click the link to browse your device's file system and select the Certificate file.

![Upload interface for certificates with instructions and file upload options displayed.](https://cdn.us.document360.io/37f15d15-eeac-4caf-9724-25918cca6992/Images/Documentation/Import-certificate.png)
4. Click **Upload**.

It redirects you to the Trust store page that displays the list of imported certificates.

### When to update the certificate?

You must update the imported CA Certificate if:

- It has expired.
- The Data system you are connecting to begins using a new self-signed or custom CA Certificate.
- Your organization's custom CA Certificate has been updated.
