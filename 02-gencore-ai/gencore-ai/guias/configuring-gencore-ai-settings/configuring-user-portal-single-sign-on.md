---
title: "Configuring user portal single sign-on"
slug: "configuring-user-portal-single-sign-on"
updated: 2026-04-27T04:25:15Z
published: 2026-04-27T21:00:23Z
canonical: "helpcenter.securiti.ai/configuring-user-portal-single-sign-on"
area: gencore-ai
modulo: gencore-ai
tipo: guia
data_captura: 2026-10-08
---

# Configuring user portal single sign-on

To configure the single sign-on, secure the following information to be configured in your IDP provider:

1. In the **Portal URL Configuration** section, copy and secure the provided Securiti Portal URL.
2. Under **Service Provider Configuration** section, copy and use the following URLs to configure your IDP provider:

| URL | Description |
| --- | --- |
| SP Metadata URL | A URL that provides the service provider’s SAML configuration details (like endpoints and certificates) to the identity provider. |
| ACS URl | The endpoint where the identity provider sends the SAML authentication response after a user signs in. |

## Configure authentication method

You can choose to configure one of the following authentication methods:

- [SAML](/latest/docs/default-securiti-user-portal#saml)
- [OIDC](/latest/docs/default-securiti-user-portal#oidc)

### SAML

To configure SAML as a sign in method:

- Configure the identity provider
- Obtain identity provider metadata
- Configure single sign-on in Gencore AI User Portal

In Securiti, you record the Service Provider (SP) metadata URL and Assertion Consumer Service (ACS) URL. You use these later when you configure the SAML service on IdP to work with Securiti.

#### **Configure the identity provider**

Configure your single sign-on service with the Securiti URLs you obtained earlier. You can also configure correlations between attributes and claim fields.

1. Log in to your single-sign-on service as an administrator.
2. If required, configure a new application or integration in the service for Securiti.
3. For the new application or integration, configure the following settings:

| Setting | Value |
| --- | --- |
| - Audience URI - Client ID - Federation Metadata - Identifier (Entity ID) | Enter the SP Metadata URL you recorded in Securiti |
| - Single sign on URL - Recipient - Reply URL (Assertion Consumer Service URL) - Destination URL - Valid Redirect URIs | Enter the ACS Url you recorded in Securiti |
| Name ID Format | Unspecified/Email |
| Client Signature Required | Off |
| - Encrypt assertion - Assertion Encryption | Off / Unencrypted |
| Force Name ID Format | Off |
| Force POST Binding | Off |
4. For the new application or integration, configure the following attribute mappings that Securiti requires from the IDP:

| Attribute Name | Attribute Keys (any one from the list) | Possible Column mapping to IDPs | Mandatory/Optional |
| --- | --- | --- | --- |
| First Name | - first_name - firstname - givenname | - Given-Name - user.firstName - X500 givenName - user.givenname | Optional |
| Last Name | - last_name - lastname - surname | - Surname - user.lastName - X500 surname - user.surname | Optional |
| Email | - email - emailaddress - useremail | - User-Principal-Name - user.email - X500 email - user.mail | Mandatory |

> [!NOTE]
> **Note**
> 
> The claim name for each name/attribute pair must not have any prefix as in the following xml:
> 
> `&lt;Attribute Name=“http://schemas.xmlsoap.org/ws/2005/05/identity/claims/email”&gt;. `
> 
> Make sure that your IDP is not adding anything to the claim.

#### **Obtain identity provider metadata**

For the application or integration, find the place in the IDP console where you obtain the identity provider metadata. The metadata is in the form of an XML file that you download, or as a URL for the file that you record to use later. Download the XML file or record the URL.

#### **Configure single sign-on in Gencore AI User Portal**

To configure the SAML sign-on in Securiti, apply the following settings:

1. In the **Authentication** section, apply the following settings

| Field | Description |
| --- | --- |
| HTTP Binding | Select the HTTP Binding as: - POST - REDIRECT |
| Source | Provide the metadata you obtained. Select the source as: - URL: Choose **URL** and enter the URL. - XML File: Choose **XML FILE** and upload the file you downloaded from the identity provider. |
| Metadata XML URL | Enter your Metadata XML URL configured from your provider. |
| Signature Algorithm | Select Signature Algorithm: - RSA-SHA256 - RSA-SHA516 |
2. Click **Validate**.
3. [Link your GenAI pipelines](/latest/docs/configuring-user-portal-pipelines) to the user portal and save the changes. Once the validation is successful, Securiti activates the **Test** button.
4. Click **Test**.

Securiti tests the configuration to make sure it is valid. If the tests succeeds, proceed to the next step. Otherwise, double-check the single sign-on configuration.
5. Once configured, copy the **Portal URL** to access the User Portal.

### OIDC

To configure settings for OIDC:

- Obtain configuration data in Gencore AI User Portal
- Configure the identity provider
- Obtain identity provider metadata
- Configure single sign-on in Gencore AI User Portal

#### **Obtain configuration data in Gencore AI User Portal**

In Securiti, you record the Assertion Consumer Service (ACS) URL. You use this later when you configure the OIDC service on IdP to work with Securiti.

1. In Securiti, click **System Settings** > **Gencore AI** > **User Portal**.
2. On the **User Portal** > **Service Provider Configuration** section, record the ACS URL information to use later.

#### **Configure the identity provider**

Configure your single sign-on service with the Securiti URLs you obtained earlier.

1. Log in to your single-sign-on service as an administrator.
2. If required, configure a new application or integration in the service for Securiti.
3. For the new application or integration, configure the following settings:

| Setting | Value |
| --- | --- |
| - Sign-in redirect URIs - Callback URL | Enter the ACS URL you recorded in Securiti |
| Grant type > Code Grants | Select **Authorization Token** |
4. For the new application or integration, configure the following attribute mappings that Securiti requires from the IDP:

| Attribute Name | Attribute Keys (any one from the list) | Possible Column mapping to IDPs | Mandatory/Optional |
| --- | --- | --- | --- |
| First Name | - first_name - firstname - givenname - name | user.FirstName | Optional |
| Last Name | - last_name - lastname - surname | - Surname - user.lastName - X500 surname - user.surname | Optional |
| Email | email | user.Email | Mandatory |

#### **Obtain identity provider metadata**

For the application or integration, find the place in the IDP console where you obtain the identity provider metadata. The metadata is in the form of an XML file that you download, or as a URL for the file that you record to use later. Download the XML file or record the URL.

#### **Configure Single Sign On**

To configure OIDC as a sign in method:

1. Add the following information.

| Field | Description |
| --- | --- |
| Client ID | Enter the Client ID |
| Client Secret | Enter the Client Secret |
| Provider URL | Enter the provider URL |
2. Click **Validate**.
3. [Link your GenAI pipelines](/latest/docs/configuring-user-portal-pipelines) to the user portal and save the changes. Once the validation is successful, Securiti activates the **Test** button.
4. Click **Test**.

Securiti tests the configuration to make sure it is valid. If the tests succeeds, proceed to the next step. Otherwise, double-check the single sign-on configuration.
5. Once configured, copy the **Portal URL** to access the User Portal.

A provider of embeddings generator refers to a system or service that generates word or sentence embeddings.
